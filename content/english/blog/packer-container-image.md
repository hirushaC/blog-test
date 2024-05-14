---
title: "Building container images with Packer and publishing to AWS ECR Repository"
images:
  - "blog/packer-container-image/media/packIt.jpg"
date: 2021-07-10T18:19:25+06:00
author: "Insighture Technology"
tags: ["Docker","Packer","Containerisation", "JMeter"]
categories: ["Technology"]
draft: false
---

When using a container solution, it is often required to have the images stored in a repository, for similar benefits that we use repositories for code. There are commonly used public repositories for containers, for example, Docker Hub. However, when you are working in a closed environment and require your code to stay within your environment, you need alternatives. Also, when I was building a solution for a client, I needed a quick reference on how to add the images to the AWS cloud. There was no simple tutorial that I could follow to achieve that. So in this short writeup, I will take you, step by step to demonstrate how I did it.



## Why Packer

Docker-Compose is a valuable and powerful tool to build container images. Many developers are not aware that other tools can be effectively used for packaging container images. Packer is a tool by [Hashicorp](https://www.hashicorp.com/) and can be downloaded from [packer.io](packer.io). There are many advantages of using packer over Docker. It allows you to take better control of your build process through conditional statements, the ability to define complex variables and use Ansible and other supported [provisioners](https://www.packer.io/docs/provisioners), all with in the JSON configuration. Provisioners allow the use of external third-party software to install and configure the machine. Some cool features can be used in the Provisioner block like retries and timeouts and these are really useful when running some external processes that may impact your builds.

## The problem

As a part of a performance and scale solution, I had written a set of Docker files with JMeter installed to allow easy execution of JMeter scripts for the development team. I wanted the container images to be sharable. Since my client was using AWS, ECR Repository was the obvious choice. Even though the production version of the containers was using Docker files, I thought of taking a step further to improve the e2e build process by using Packer to build the container image and push it to AWS ECR Repository. For the purpose of this writeup, I will create EC2 images using available Ubuntu AMI, though it is possible to use the **source "docker"** and build Docker images.

## Install Packer

Packer can be [installed](https://www.packer.io/downloads) directly from the packer site. I was using a Windows machine and installed using the provided windows installer.  

## Create the configuration file

I chose to create the configuration files as .hcl extensions, abbreviated for HashiCorp Configuration Language. The more recent HCL2 is what I preferred to use for its ease of coding.

### Define variables
```JSON
variable "ami_name" {
  type    = string
  default = "insi-perf-ami"
  # default = "${env["CUSTOM_AMI_NAME"]}"
}

variable "tag" {
  type = string
  default = "insi-jmeter"
}
variable "tag_version" {
  type = string
  default = "0.1"
}

variable "region" {
  type = string
  default = "us-east-1"
}
variable "jmeter" {
  type = string
  default = "apache-jmeter-5.4.1"
  # default = "${env["JMETER_VERSION"]}"
}

locals { timestamp = regex_replace(timestamp(), "[- TZ:]", "") }
```

In the above code snippet, I have defined a few variables that I will reuse in the configuration later. You can provide environment variables to populate the variable names. In the code above, I have commented (# in the beginning denotes a comment) the **default** using environment variables as a reference for those wanting to use externalised variables.
> **"locals"** block can be used to define local variables like timestamp in the code above.

## Define source block
Source blocks allow us to define reusable builder configuration. Here is the next code example showing the source block that is configuring a t2.micro **instance_type** and using **filters** to search my the right **AMI** as per your requirement.

```JSON
source "amazon-ebs" "insi-perf" {
#  access_key    = "${var.aws_access_key}"
#  secret_key    = "${var.aws_secret_key}"
  profile = "insighture"
  ami_name      = "${var.ami_name} ${local.timestamp}"
  instance_type = "t2.micro"
  region        = "${var.region}"
  source_ami_filter {
    filters = {
      name                = "ubuntu/images/*ubuntu-xenial-16.04-amd64-server-*"
      root-device-type    = "ebs"
      virtualization-type = "hvm"
    }
    most_recent = true
    owners      = ["099720109477"]
  }
  ssh_username = "ubuntu"
  force_deregister = true
}
```
AWS credentials can be passed in different ways, I used locally setup profile, you could also set the environment variables.
> Use secure ways to provide credentials to the configuration. **Do Not** put credentials into the configurations.

> **"owners"** is a required field that is used as a security layer to ensure that right AMI's are used during the builds. Use self if you are looking for AMI's within the scope of provided AWS credentials.

## The Build Block
The final piece in  the configuration is the build block. This is where you provide
- **source** reference defined above
- **provisioners** to configure the instance and
- **post-processors** which we will use to tag and push the image to the repository

```JSON
build {
  sources = ["source.amazon-ebs.insi-perf"]

  # install ansible
  provisioner "shell" {
    inline = [
    "sleep 30",
    "sudo apt-get clean",
    "sudo apt-get -y update",
    "sudo apt-get install -y software-properties-common",
    "sudo apt-add-repository ppa:ansible/ansible",
    "sudo apt-get -y update",
    "sudo apt-get install -y ansible",
    ]
  }

  # install jdk and jmeter
  provisioner "shell" {
    inline = [
    "sudo apt-get clean",
    "sudo apt-get update",
    "sudo apt-get -qy install wget default-jre-headless telnet iputils-ping unzip",
    "sudo apt-get install -y openjdk-8-jdk",
    "sudo apt-get install -y ant",
    "sudo apt-get install dos2unix",
    "sudo apt-get clean",
    "sudo mkdir /jmeter",
    "sudo cd /jmeter/",
    "sudo wget https://archive.apache.org/dist/jmeter/binaries/${var.jmeter}.tgz",
    "sudo tar -xzf ${var.jmeter}.tgz",
    "sudo rm ${var.jmeter}.tgz"
    ]
  }

  # set env vars and path
  provisioner "shell" {
    inline = [
    "ENV JMETER_HOME /jmeter/${var.jmeter}/",
    "ENV JMETER_BIN $JMETER_HOME/bin",
    "ENV PATH $JMETER_BIN:$PATH",
    # Install Plugin-Manager
    "cd $JMETER_HOME/lib/",
    "wget https://repo1.maven.org/maven2/kg/apc/cmdrunner/2.2/cmdrunner-2.2.jar",
    "cd $JMETER_HOME/lib/ext",
    "wget -O jmeter-plugins-manager-1.6.jar https://repo1.maven.org/maven2/kg/apc/jmeter-plugins-manager/1.6/jmeter-plugins-manager-1.6.jar",
    "java -cp jmeter-plugins-manager-1.6.jar org.jmeterplugins.repository.PluginManagerCMDInstaller",
    # Add Plugin-Manager to the Path
    "ENV PATH $JMETER_BIN/PluginsManagerCMD.sh:$PATH"
    ]
  }

  provisioner "shell" {
    script = "./provisioners/scripts/plugins.sh"
  }

#  provisioner "ansible" {
#    playbook_file = "./provisioners/ansible/playbook.yml"
#  }

  post-processor "docker-tag" {
    repository = "xxxxxxxxx.dkr.ecr.us-east-1.amazonaws.com/insi_test"
    tag = ["${var.tag}","${var.tag_version}"]
  }
  post-processor "docker-push" {
    ecr_login = true
    aws_profile = "insighture"
    login_server = "https://xxxxxxxxx.dkr.ecr.us-east-1.amazonaws.com/insi_test"
  }
}
```    
The above code shows a mix of different provisioners that have been used to configure the image. **shell - Inline** allows you to write shell commands in the configuration. For modularity you could also use **shell** and provide the location of the script.
```JSON
provisioner "shell"  { script =  "./provisioners/scripts/plugins.sh"  }
```
plugins.sh has the plugins I need for my JMeter install. For example
```bash
# 3 Basic Graphs
PluginsManagerCMD.sh install jpgc-graphs-basic=2.0
# 5 Additional Graphs
PluginsManagerCMD.sh install jpgc-graphs-additional
.
.
```
We could also easily install Ansible as in the code above using **shell - inline**  provisioner.
```bash
"sudo apt-get install -y ansible"
```
and then use a **playbook** to further configure our image for example
```bash
  provisioner "ansible" {
    playbook_file = "./provisioners/ansible/playbook.yml"
  }
```
Finally the **post-processor** blocks shows how we tag and put the image in the ECR repository using **docker-tag** and **docker-push**.
```bash
  post-processor "docker-tag" {
    repository = "xxxxxxxxx.dkr.ecr.us-east-1.amazonaws.com/insi_test"
    tag = ["${var.tag}","${var.tag_version}"]
  }
  post-processor "docker-push" {
    ecr_login = true
    aws_profile = "insighture"
    login_server = "https://xxxxxxxxx.dkr.ecr.us-east-1.amazonaws.com/insi_test"
  }
```
<br/>

## Running Packer build
Packer is easy to use. First we can use the CLI to validate the packer file
```bash
packer validate yourconfig.hcl
```
If there is no error on CLI then everything should just be fine when you run the build using the build command.
```bash
packer build yourconfig.hcl
```

This will output each step on the CLI as it completes and if there is an error it will flag it appropriately. Otherwise, the image will be created and pushed to the repository as instructed in the post-processor. It is possible to build images for various other services with the same configuration at the same time. For more information, you can visit the detailed [documentation](https://www.packer.io/docs) on the [packer website](https://www.packer.io/).
