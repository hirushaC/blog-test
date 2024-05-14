---
title: We Migrated Our Blog from Static Site to Decap CMS (Netlify)
image: /article/shubham-dhage-mjl0yidsi18-unsplash.jpg
date: 2023-11-24T14:20:03.979Z
author: Insighture Technology
tags:
  - ContentManagementSystem
categories: []
draft: false
---
## **Introduction**

Insighture is in its growth phase. We recently set strategic goals that involved a spike in content marketing initiatives and pushing out fresh blog content for our loyal readers and refined target audience, especially with the milestones we are making at the office and the topics our chapter leads are subject matter experts on. If we overcome a challenge as a team, why not share our learnings here for the whole tech community to benefit from?

In this blog post, we will share how we successfully migrated to a modern open source CMS (Content Management System) called Decap (formerly Netlify) after relying on a static site generator for nearly 4 years.

The migration was necessary due to the timelines we’d set for ourselves in terms of our blogging strategy. We needed fresh content out in a timely manner. Waiting for the schedules of our in-house developers to free up was just not going to cut it. They were smashed with client work. Our content manager needed full control over the content pipeline. With the help of a new member of our team, a hands-on developer, we incorporated the CMS successfully into our blog URL.

## Key steps we took ✒️

* Assessment of current content architecture and data structure.
* Assessment of potential Jamstack CMS vendors for static websites like yours based on the following factors — scalability, stability and cost.
* Use of customized scripts for mapping and cleaning up content.
* Use of the selected CMS migration plugins, APIs, and tailored scripts for seamless content, metadata, and media asset transfer.
* Extensive testing in staging environments to confirm data integrity and functionality after the migration was over.
* Use of Slack collaboration tool for ongoing te­am communication and task management during the­ migration process.
* Writing up clear documentation for the Netlify configuration for website owners and sys admins to be informed on the migration especially from a security angle.
* Understanding the limitations of a Static Site Generator ⚓

### The old setup we had

Usually, we produce conte­nt offline or in a text editor. The­n, we would turn to Hugo to transform it into HTML files that form the site. The­se files delive­r directly to visitors, no need for cre­ating fresh content eve­ry time on the serve­r. This method was more manual, more hands-on than the usual CMS platforms. It is basically how a static site ge­nerator functions. Here, conte­nt is ready-made and static, instead of dynamic generation eve­ry time someone re­quests.

**There were plus sides we will admit!**

Hugo may not offer a usual CMS se­tup, but it’s pretty good with content creation and handling via Markdown files and othe­r types. In other words, you can add fresh conte­nt with ease, no nee­d to mess around with coding.

Despite lacking a standard CMS backe­nd, Hugo still offers flexibility.

The site would load quicker, and was more se­cure because the­re’s no need for database­s or server processing.

Still, there was an opportunity cost here.

### High time to migrate.

The fact that you have to do more and more work by hand to create, handle, and send information is the clearest sign that your system is getting old. Just like we said, we didn’t have an existing automated CMS. Even though this method worked at first, it caused a lot of problems as our online presence grew and goals shifted. Since there wasn’t a specialised CMS, there wasn’t a single place to control the content, which made it hard to make changes and improvements. Each change needed to be made by hand in the system, which made the process slow and prone to mistakes. This slowed down content speed and development.

### Specific CMS-related pain points we had. 🆘

* The absence of a CMS made updating blog articles hard and took a lot of time. It required changes to the back end, which slowed us down and made it harder to meet market needs quickly. For instance, push out content types to drive mission-level marketing goals.
* Our static website had certain limitations right off the bat. It was hard to set up collaborative writing and version control, which made it harder for technical and content teams to work together, and for content to be changed in real time.
* As our content library expanded, it was also hard to keep track of all the different types of content and formats too. The lack of a structured CMS framework made it less flexible and effective to organise and categorise the content. This affected adaptability and maintenance.
* Automating social sharing, plagiarism detection and advanced SEO functions for example can be done using standalone plugins instead of employing a solution with a whole suite of tools. This was a tradeoff we were ready to make.
* Our team’s morale was dropping as they had to make time for developer coding in the middle of dead-line driven client deliverables. It was hectic!
* Both our temporary web admins and visitors had bad experiences due to content formatting errors made worse by an extensive coding process, and little to no space for website optimisation causing readability issues.
* We had our minds set on a new target audience in alignment with the latest strategic direction and brand vision and we were unable to reach those audiences with fresh content churned out.
* Cost was one of the major factors we were looking at when looking for CMS options. Headless CMS options were slightly over budget and there were inconsistencies in the user reviews on the support that we would actually receive.
* Because of these specific problems, we decided to look into other options and weigh the pros and cons according to our exact requirement. This led to the choice to move our blog to Netlify (Decap). This change was necessary to solve these problems and keep our digital platform strong, dynamic to a certain degree, and able to meet content needs now and in the future.

### Why Choose Netlify (Decap)? 💯

Decap CMS, a rebranded version of Netlify CMS, was launched in February 2023. Netlify, a trusted platform on Jamstack, is a modern CMS that aims to revolutionise static site management. Decap CMS is an open-source React app that wraps the Git workflow using GitHub, GitLab, or Bitbucket API. It offers a fast, web-based UI with rich-text editing, real-time preview, and drag-and-drop media uploads.

![](/article/theregisti-ziszilqlsom-unsplash-1-.jpg)

Decap makes it easy for teams to handle content by combining a lot of strong features into one. These features include version control, content versioning, and an intuitive interface. Its easy-to-use process makes it easier to create content, work together on it, and distribute it. This makes handling basic websites more flexible and productive. This is summed up in the CMS vendor comparison below -

![](/article/netflify-cms-versus-headless-cms-2-.png)

## Planning the migration 🪽

### Review of the old system

The old content management system (CMS) was carefully reviewed before the transfer process began. This included -

* Technical evaluation where we took a close look at the current CMS design, including the database layout, content types, how information is handled, and what other systems it depends on.
* Performance analysis is the process of looking at the system’s performance data, finding problems, and figuring out what needs to be fixed.
* We took stock of all the content that already exists, sorting it into categories based on how relevant it is, and figuring out how complicated its structure is.
* Finding out what content creators, managers, and users don’t like and what they’d like to see changed by getting feedback from them.

### Setting goals for migration

To help with the transfer process, clear goals that could be reached were set -

* Content integrity — Making sure that all content, including information and video, is sent to Netlify (Decap) correctly and without any loss or damage.
* Improved performance -This is meant to make websites run faster, make information easier to find, and improve the general user experience.
* Scalability and flexibility — Using Netlify’s (Decap) tools to make it easy to handle material, make changes, and add more users in the future.
* Minimising downtime — Making plans for a smooth transfer that doesn’t affect the live website too much.

### Risk and security precautions we took

A very important part of the planning phase was coming up with ways to deal with possible risks.

Data loss prevention — Setting up backup systems to keep information safe while the transfer is happening.

Making sure that the old content management system (CMS) and Netlify (Decap) can work together without any problems by testing their compatibility.

Making backup plans and rollback steps in case something goes wrong during the move that wasn’t planned.

Making sure that cross-functional teams working on the transfer process can communicate and work together well so that any problems can be fixed quickly.

## Executing the migration 🪛

When we set up our system, we created a directory called ‘admin,’ which had both a configuration file and an HTML page called index.html. We implemented a Netlify Identity authentication script into this framework, granting administrator access to the sign-in and Forget Password pages. Following that, we created a Decap CMS script, which provided a framework for page development and enabled Decap’s features inside our system.

### There were a couple of required settings from Netlify’s end.

When we visit a deployed site, we can see the site configurations, click identity, and enable identity.

![](/article/1.png)

Inside the identity folder, we can find the enable git gateway option and click enable.

![](/article/2.png)

It will ask you to authenticate and generate a token.

![](/article/3.png)

Since we are only allowing users to login from the portal, in Decap (Netlify), we enable the invite-only option.

![](/article/4.png)

Send an email invitation to the required person.

![](/article/5.png)

After getting the verification link from the Netlify admin, the user will be able to set the custom password. Finally, they will be able to login to the CMS portal and post the blogs.

![](/article/untitled-design-25-.png)

The Home view inside Decap CMS — Easy publishing of blogs!

![](/article/image3.png)

## Lessons learnt and best practices

One of the primary takeaways was the significance of meticulous pre-migration planning. Understanding the intricacies of the legacy CMS, setting clear migration goals, and anticipating potential risks proved instrumental in executing a successful transition. Additionally, fostering effective collaboration among diverse teams involved — developers, content creators, and IT support — was crucial for a streamlined migration experience.

### Extensive testing

At each step of the transfer process, you should do thorough tests of connectivity, content checking, and speed.

Check the accuracy, usefulness, and performance of the data to make sure the transfer goes smoothly.

### Focus on collaboration

Keep the lines of communication open and uniform between all the teams working on the transfer.

Regular reports and sharing of information in a clear way help to handle issues quickly.

### Adequate CMS trainings

Set up regular training events for users to get them used to the new CMS platform.

Make it easier for people to get used to the new method faster by giving them tools and help.

## A few resources to add to your migration toolkit. 🧰

Of course this depends on your website framework and technology, strategic goals and content needs.

* [Netlify (Decap) Documentation](https://decapcms.org/docs/intro/) providing detailed guides and tutorials for using Netlify’s CMS platform.
* [A comprehensive side-by-side comparison](https://cloudcannon.com/jamstack-ecosystem/jamstack-cms/) of CMS built for JamStack static sites.
* [Discourse forum on selecting the best open source CMS for Hugo](https://discourse.gohugo.io/t/what-is-the-best-open-source-cms-for-hugo/34728?page=3)
* [GitHub Repository for Migration Scripts-](https://github.com/decaporg/one-click-hugo-cms) Access open-source scripts and tools used for data migration and content transformation during the process.

**Web Performance Testing Tools-**

[Lighthouse by Google](https://chrome.google.com/webstore/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk): A tool for assessing website performance.

[GTmetrix](https://gtmetrix.com/): Provides insights into website performance and optimization strategies.

Thanks for reading. Hope you found this blog useful! The transition from the old system to Netlify (Decap) was not just about adopting new tools. It was about upgrading to a faster, more flexible method of managing blog content. The entire process involved careful planning, extensive testing, and collaboration. The change not only improved the efficiency of our content editors but also demonstrated the importance of proper preparation and cooperation in achieving cross-functional goals.