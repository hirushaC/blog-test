---
title: The Strategic Impact of Technical Debt
image: /article/blog-tech-debt-is-forever-hero.jpg
date: 2023-10-30T18:03:02.948Z
author: Insighture Technology
tags:
  - Technical Debt
  - Technology Leadership
categories: []
draft: false
---
**Target audience: CTOs and CIOs**

**Introduction**

In the fast-moving world of technology and innovation, leaders face a growing list of challenges. As a new release approaches, questions start to emerge:

> **"Have we tested the upcoming features thoroughly?"**
>
> **"Will our tests catch all potential issues?"**
>
> **"Can our application handle the new customers coming on board?"**

These concerns are not unique and are shared by tech leaders dealing with changes in integration partnerships and the constant push for new features. As you wonder why new features take longer to arrive or why a simple change seems to drag on, you’re not alone. The question “Why didn’t the developers get it right from the start?” is something many leaders such as yourself have in mind. If you’ve ever found yourself asking these questions, read on.

In this article, we’ll delve into a critical aspect of software development that is often misunderstood: *technical debt*. Tech debt is something that can have a significant impact on an organisation’s overall strategy, competitiveness, and financial well-being. A common misconception is that it is a technical issue. However, tech debt actually impacts all aspects of your business one way or the other.

### **So what is it?**

Technical debt is a term coined by software developer Ward Cunningham in 1992. He defines it as the cost of additional rework caused by using the quickest solution rather than the most effective one. The term has since evolved to refer to both tech debt and code debt. Let’s look at that.

![Man holding a giant heavy credit card ](/article/reasons-why-software-practitioners-2-.png)

Imagine your code as a credit card. Taking on technical debt is like making minimum payments, allowing the interest to accumulate. Eventually, you’ll have to pay a price to get yourself out of the red. Just to clarify, having tech debt in the core implementation is what is actually undesirable. In this sense, prioritising it is crucial.

**The metaphoric Tug of War**

In software development, technical teams, product owners and executives often make **trade-offs** in terms of two things — software quality and delivery timelines.

The product teams want to expand the product’s features quickly, while the engineers express concerns about the impact on the product areas and codebase. Dev teams want to create something robust so the complexity of architecture, code, and design increases. This in turn affects delivery schedules and product improvements. Getting flack from customers and execs, the product teams push for quicker delivery, causing the engineers to reluctantly give in. As new features are added, bugs appear and are fixed quickly as a band-aid solution, creating a black hole of technical debt, pushing timelines further and causing development stalls. It’s a vicious cycle.

Technical debt is inevitable and can be created and exacerbated at different levels of the organisation. It is not so much a case of preventing it than of managing it.

**It is also not about developers taking shortcuts as is how it is often incorrectly perceived. Rather it is about the decisions made during the engineering planning process or impact analysis after the kickoff.**

There are two types of technical debt: intentional and unintentional.

**Intentional debt**

![Team sitting at a table at a meeting with laptops looking a screen with sticky notes on the wall behind](/article/jason-goodman-vbxyfxlgpjm-unsplash.jpg)

Sometimes, at the initial stages, we choose to overlook the tech debt to release the Minimum Viable Product (MVP). We plan to address the debt at a later stage with a broader scope in future releases.

For example, if we require a software solution with 10 user stories, and some of the user stories appear to be complex due to implementation challenges, we may decide to skip those for the V1 release and leave the associated tech debt unresolved. Instead, we focus on delivering whatever is feasible for the MVP launch. Project managers may ask teams to skip perfect application instrumentation and focus on testing new features. It is important to remember that this is a deliberate design choice considering the cost and future impact on the software.

**Unintentional debt**

Software systems can break down over time if they are not maintained (updating libraries, design patterns etc.) or evolved (creating new features and capabilities in due course). Evolving the codebase and neglecting maintenance can both create unintentional technical debt for you by either making the system more complex and stifling innovation respectively.

Technical teams may also fail to keep up with future design patterns, as seen in the monolith-to-microservices situation. They may have written their codebase in a way that made sense at the time not realising that they would need to scale to a million users. This transition could be costly. Of course, sloppiness or a lack of technical skill in software engineering can also lead to tech debt.

**Keep in mind that tech debt is not a real issue unless it requires your teams to touch the code. It is only considered debt if there is a slowdown in delivery, stifled innovation, and unpredictability in whether you can change the code, preventing it from being run in a production user-facing capacity.**

> “But technical debt is technical, right? Why should non-developers care?”

Last December, Southwest Airlines experienced a massive debacle, causing nearly 17,000 flights to be canceled, shutting down two-thirds of its operations and losing over $1 billion in revenue. The reason? Outdated software.

![Man at airport at Southwest Airlines counter](/article/download.jpg)

**The hidden costs of technical debt**

The impact of accumulated technical debt extends broadly across different parts of your organisation’s ecosystem.

> “Technical debt makes building new features that should be easy, hard, and features that are sophisticated, impossible.” –Christian Nelson, VP of engineering at Carbon Five

**Impact on Code** 

According to The Developer Coefficient by Stripe, the average developer spends 13.5 hours a week on tech debt out of the 41.1 hours they are on call.

![](/article/0_dwsfz0ezrjrw4cg2.png)

This is the reality.

Technical debt can lead to slower development cycles, defects, and bugs, which can negatively impact the product, increase maintenance costs, and degrade user experience. Engineers may not write clean, well-organized code due to time stress, making it more complex and prone to bugs. Additionally, compromising design and development practices can lead to lower code quality, generating long-term issues and making it difficult for engineers to maintain the codebase, affecting product stability and sustainability.

**Impact on Product** -To reiterate, delays in software releases can hinder the pace of a high-growth SaaS company. For example, launching a product in December instead of October could significantly impact Monthly Recurring Revenue (MRR), potentially affecting the company’s growth by up to 30%. Even if growth remains constant at 15%, shipping two months later could significantly impact your company’s MRR, potentially affecting its future success.

As mentioned earlier, quality issues can compound over time and create fresh problems such as employee and customer churn. In a customer-facing capacity, it may potentially lengthen the downtime of your product. For example, the loading speed of a website will be affected if there are too many lines of code for a basic feature or too many callbacks to a single function. And no matter how appealing your product seems on the app, if it is sluggish, you are letting down your customers. Poorly written code also increases security risks, creating unexpected vulnerabilities and increasing the likelihood of major incidents like data security breaches.

**Impact on Team** -Developer burnout is a serious problem. Negotiating a deadline extension is one of the ways that developers do try to address future technical debt. However, in the short term, payment of the debt happens through practices such as code refactoring, design refactoring and making code adhere to good programming practices. This all takes time.

**Impact on Morale -** Developer Burnout

Developer morale is declining due to technical debt accumulation, reducing productivity and causing errors, shutdowns, and quality concerns. As remote work becomes a long-term solution, the issue worsens, emphasizing the need for better understanding and prioritization of features. Dissatisfied or demotivated engineers are more likely to leave, harming your organization, workload, and team effectiveness. Neglecting technical debt can lead to difficulty in retaining expertise and recruiting issues.

**Impact on Business**

As illustrated, product managers, dev teams and executives are technically all on the same side. They just have different goals and perspectives. In the end, the competitiveness of the entire business hangs in the balance. Consider the high-level repercussions of not addressing the debt:

* **Customer dissatisfaction**: Due to poor user experience, tech debt nearly always has a negative correlation with customer happiness. This results in increased costs due to more tickets and customer assistance, as well as a loss of sales and renewals due to decreased client retention. On a side note, building software products is always going to be challenging because user requirements are changing at the speed of light. It’s a fast-paced industry and there are multiple competitors. The moment requirements change, there is potential tech debt.
* **Reduced innovation:** When technical debt is substantial, developers must continue to service the issues rather than investing time to create inventive new business-value capabilities. The team will be unable to respond rapidly to market opportunities or changes. Codebases that are burdened by debt are less flexible. Innovation frequently necessitates the ability to pivot, experiment, and rapidly integrate new features. This agility is hampered by technical debt.
* **Cost increases:** Technical debt can make it more expensive to maintain and develop code. This includes fixing issues, boosting performance, and dealing with lost productivity due to delays. It also leads to additional customer support charges and prevents investment in new features, innovation, or market expansion. Focusing on technical debt can lead to missed opportunities and market advantages that cannot be capitalized on.
* **Reduced revenue:** Customer unhappiness as a result of technical debt results in lower customer retention and ineffective marketing spending.
* **Brand and reputation:** If technical debt is significant, it can harm your company’s brand and reputation, jeopardising its survival. It can result in decreased software quality and reliability. With defective or unreliable software, you lose credibility in a market where consumers increasingly seek flawless and trouble-free experiences.

Final thoughts.

### **You may need to change your approach to tech debt...**

Reducing tech debt is one of the productivity skills that a technology leader needs to master. It can seriously impact your bottom line. But don’t get bogged down with this, leaders. These are the difficulties that your company faces on a daily basis. They aren’t just inconveniences. They’re the fabric that shapes your product. It all comes down to making the decision to keep debt under control. 

In the recently published paper [Software practitioners’ point of view on technical debt payment](https://www.sciencedirect.com/science/article/abs/pii/S0164121222002308), we see why tech debt payment is so challenging these days.

![](/article/untitled-design-16-.png)

**Conclusion**

Digital leaders remember, market pressure is real and your company may have resource limitations. To top it off, what you are currently building may be complex and involve creating loads of new dependencies. Not everything is within your control. But in the end, you need to live with the trade-offs that you are making. Awareness and adjustment is key!

You must embrace technical debt reduction as a strategic imperative. It’s not just about clean code, but about securing your organisation’s future in a rapidly evolving environment. Ignorance is not bliss in this instance.