---
title: Asp.Net Core Options Pattern
image: /article/asp-dotnet-core-options-pattern-banner.jpg
date: 2021-07-16T18:19:25+06:00
author: Insighture Technology
tags:
  - ASP.Net
categories:
  - Technology
draft: false
---
Options pattern provides an elegant and an easy way for you to load your application configurations into your classes at runtime and access your configuration values from instance of the class rather then injection IConfiguration service. To use the options pattern in ASP.NET Core, you need to install the **Microsoft.Extensions.Options.ConfigurationExtensions** nuget package.

> To get the maximum benefit of using the options pattern, you would
> typically want to use separate classes to represent a group of related
> settings in isolation.

### Below are some of key principles you get as benefits by adhering

* **Separation of concerns:** The settings used in different modules are decoupled from one another
* **Interface segregation principle:** The classes that represent these settings depend only on the configuration settings that they would use

### Options pattern configuration

To understand the options pattern configuration, consider the following example of a **IntegrationSettings** section in your **appsettings.json** file.

![](/article/img-2.jpg)

Inorder to use the options pattern to load the configurations in to a
class at runtime, you need to create a class as below to hold the values
loaded from the configurations.

![](/article/asp-dotnet-core-options-pattern-image2.png)

You can now use the **configure extension method of IServiceCollection** to
bind your settings class to your configuration as shown below.

![](/article/asp-dotnet-core-options-pattern-image3.png)

### Read configuration data in a .NET Core Api controller

Now to read configuration data in the controller. You can use the **IOptions<T>** interface’s Value property to retrieve the instance of the settings class.

![](/article/asp-dotnet-core-options-pattern-image4.png)

As shown above, you can access your configuration values from your
**_settings** class similar to how you access any data from another class
and you no longer need to inject **IConfigurations** class as a dependency
to your controller or service.

> **Next time when you are dealing with configurations use the option patterns as it brings lots of flexibility to manage your configurations data.**

Using Options Pattern helps you isolate your configurations to the code  where its required.

**Thank you!**