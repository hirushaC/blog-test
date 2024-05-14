---
title: "Agility in EdTech: How an Integration Connector Simplified Teacher
  Screening and Onboarding"
image: /article/giovanni-gagliardi-fvt3t9ioaji-unsplash.jpg
date: 2024-05-03T19:43:00.000Z
author: Insighture Technology
tags:
  - EdTech
  - Integrations
categories: []
draft: false
---
Target audience: Startup founders, CEOs, CTOs 

Admin burden and manual task overload in education is a continuous issue, eating up time and resources. EdTech helps by automating tasks such as student registration, grading, and attendance tracking, and managing data, like with student info systems and learning management systems (LMS). But challenges such as integration problems and ongoing training still pose an issue. Making your mark in EdTech largely depends on enhancing the customer experience, just as education itself is an immersive journey. To excel in EdTech, it is important to pay attention to both the customer experience and business agility. This not only betters the learning experience for students but also helps educational institutions who want to gain entry to EdTech to be able to adapt and thrive. If you're curious about how your team and respective EdTech solutions can stand out in this crowded field, or if you are simply interested in knowing practical tips for succeeding in EdTech consulting, keep reading. 

In this blog post, we will share a success story of how we successfully implemented a solution for an EdTech platform offering educational courses at the K-12 level (kindergarten to Grade 12). 

> The solution added great value to the verification process of educators signed up  to teach on the platform resulting in a high quality of service delivery to students and a trusted brand sentiment for the solutions provider. 

![](/article/compare-fibre-jioffi3w7ia-unsplash.jpg)

# Client Overview

EdTech usage among K-12 schools has increased by 99% since 2020. To add to that, 79% of teachers surveyed are using EdTech each day.

Our client, an innovative Edtech company in Melbourne, Australia, which specialises in personalised learning for K-12 students using AI algorithms. It is a learning marketplace of sorts. They partnered with an enterprise-level education partners i.e. universities, colleges, educational institutions and top talent agencies  for access to experienced educators and have since been providing high quality on-demand courses to this age bracket for the past 5 years. Insighture has been providing their EdTech platform with tailored consultancy services for a little over 3 years, helping them scale IT talent resources, pivot effectively, and enhance their service offering with top-tier solutions architecting, security hardening and more. We rapidly implemented innovative features, including third-party integrations, to boost efficiency and empower their business growth. One impactful integration was the connector we implemented for their e-learning platform. 

# The Challenge: Difficulty Screening and Onboarding Qualified Teachers and Educators

Despite their modern technology stack, the client was facing challenges in providing seamless integration with various HR systems used by their education partners supplying their teachers. The platform also needed to sync the progress between the existing systems of those institutions and the EdTech platform. The intended result was to be an up-to-date database of educators with biodata cross-checked for qualification criteria and teaching history and records indicating fitness and eligibility to teach young students. The learning platform currently faced the challenge of manually inputting data into the platform through the user interface or resorting to bulk data upload via CSV files. A recurring issue is the necessity to extract data from their talent partner’s existing HR systems and subsequently convert it to meet the EdTech platform’s specific format. This is precisely where the implementation of an integration connector proved invaluable.

**History of the Client Engagement**

Insighture’s engagement with the client commenced with a proposal to implement a captcha-based scanner aimed at facilitating student verification. Since then, Insighture established a collaborative partnership, working as an extended team to handle various development projects. 

The EdTech company itself was aware that the systems they had at the time were not fulfilling their objectives and creating loads of rework amd maintenance overhead.

> The client also knew that Insighture would be a good solution due to their experience is security and compliance, and dealing with integration complexity on a daily basis for clients of all sizes and domains.

![](/article/jeswin-thomas-2q3ivd-hsam-unsplash.jpg)

# The Solution

We solved the challenge of manual data input and conversion for teacher onboarding for this Edtech client by implementing a connector that integrated with popular HR systems. This connector enabled its educational talent partners who use popular HR systems to integrate into the platform without any hassle.

The integration connected supported the following popular HR systems currently: Humanforce, UCare, ELMO, connx

**Connector Integration Benefits**

* Efficiency - Automating data transfer between the EdTech platform and HR systems eliminates the need for manual data entry, saving the platform administrators valuable time and effort.
* Accuracy - By ensuring real-time synchronisation of teacher data and progress updates, the integration reduces the risk of errors and discrepancies, providing the EdTech company with accurate insights into each teacher/educator profile.
* User adoption - With a seamless integration experience, such educational talent partners are more likely to embrace the EdTech platform as part of their teaching toolkit and added value services, leading to increased adoption rates among schools and districts and also a better screening process of the talent they have.
* Scalability - The connector integration allows the client to scale their platform implementation across a diverse range of educational institutions, accommodating different HR preferences and infrastructure setups without compromising functionality or user experience.
* Data sync between the EdTech platform and the HR system through scheduled updates was another crucial benefit thus reducing the load on existing applications due to sheer volumes of data exchanges due to horizontal scaling. 

# **How We Successfully Executed The Integration Connector**

Going into it, there were challenges we faced prior to the implementation stage:

1. Varying ingress/egress data sources (REST APIs, GraphQL, SFTP)
2. Serverless architecture to save cloud costs as the systems can run on their own schedules saving expensive compute costs
3. Data flow happens on schedules not real time since it is not efficient to run infrastructure full time
4. Compatibility with varying data structures from different data sources on ingress/egress

**System Design**

![](/article/image1.png)

## **Pillars of Our Successful Execution**

**Strategic Alignment and Consultancy-Led Solutions Architecture**

We began by conducting a comprehensive evaluation of the client's core business objectives, carefully adapting our strategic approach to align with their goals. We delved deep into the project backlog, bridging any gaps between technical requirements and business needs.Through that process, the EdTech company communicated the administrative burdens they had and our leads conceptualised this connector solution, presenting it to them only when it was ready to be implemented.

* Serverless implementation of an integration connector: In our endeavor to enhance the efficiency of our integration connector, we went 100% serverless. By embracing a serverless implementation, we transformed our approach, eliminating the need for dedicated servers and adopting a dynamic resource allocation model. This removed the requirement to run servers all day for a specific task that should in reality take only a few minutes to run which saved us from compute costs skyrocketing.

**Performance Strategy for Agility and Innovation**

We have always maintained a culture of creativity evidenced by our active RnD unit and Centers of Excellence, enabling rapid development and deployment of new features. The client was able to benefit out of that readiness to implement solutions dynamically. Proper testing strategies were employed before this release in parallel with the client, and a robust testing framework was built to support the evolving business logic. This framework enabled continuous monitoring and optimisation, allowing for real-time adjustments to ensure optimal performance. Proactive security measures were implemented to address web vulnerabilities effectively.

* **Horizontal scalability in data transfers connecting to multiple systems:** As we expanded the capabilities of our integration connector, facilitating seamless data transfers between multiple systems emerged as a critical requirement. Through horizontal scaling, we ensured that our connector remains responsive and reliable, even as data volumes and user demands fluctuate. This scalability empowers our connector to accommodate growing number of new clients, varying transfer requirements, facilitating uninterrupted connectivity and data exchange across diverse systems and environments.
* **Dynamic adapter pattern for adaptable integration:** We wanted the connector to be adaptable to diverse data sources and systems. To achieve this, we developed and implemented a dynamic adapter pattern. This adaptability enables seamless integration with client-specific systems, regardless of their underlying architecture or data formats. By dynamically configuring integration flows and intelligently utilising core components, we ensure compatibility and interoperability across disparate systems and platforms, delivering vendor-neutral data templates and maximising the value of the connector.

# The Result?

Insighture's remote teams brought a level of proactive communication and collaborative problem-solving that made a difference to the client’s business, ensuring seamless coordination and timely resolution of challenges during the integration process.

The integration connector on the EdTech platform yielded several positive business outcomes, including:

1. With seamless integration with popular HR system providers, the EdTech platform now had **easy access to the benefits of a speedier and more thorough screening process for teachers**, empowering them to deliver quality educational experiences that meet the needs of every student. 
2. **Administrative burden cut by 80%.** Streamlined data transfers and automated processes reduced manual input and administrative burden, enabling platform developer and admin staff to focus on core tasks such as platform maintenance and security.
3. Data synchronisation between systems minimised errors and discrepancies, ensuring the **integrity of information** across the EdTech platform and the HR systems.
4. Horizontal scaling capabilities allowed the EdTech platform to **accommodate growing data loads and user demands**, supporting business expansion without performance degradation.
5. **Seamless integration with partner HR systems** improved the overall user experience, especially for the platform owners, by providing a more cohesive and efficient platform.
6. By enabling **uninterrupted connectivity and data exchange**, the integration connector empowered the platform to scale and adapt to evolving business needs, facilitating growth and competitiveness in the market.

# Conclusion

By implementing a connector integration solution, our client successfully addressed the interoperability challenges hindering the widespread adoption of their personalised learning platform, in other words teacher signups. As a result, the client experienced increased customer satisfaction from their student end-users and their parents, improved user retention, and accelerated growth in their market presence within the EdTech industry as a result of meeting with higher standards of security and safety for young students and also education.

If your organisation is facing similar challenges or seeking to unlock new opportunities in the edtech sector, our team stands ready to help. With our expertise in integration connector  solutions and a track record of driving success for clients, we're ready to collaborate with you in achieving your strategic objectives. [Reach out to our Solutions Lead](https://www.insighture.com/contact/) today to explore how our consultancy services can empower your organisation to thrive in the exciting constantly changing world of EdTech.
