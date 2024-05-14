---
title: How to Optimise Code Reviews
image: /article/img_0385.jpg
date: 2023-10-25T06:42:19.444Z
author: Insighture Technology
tags:
  - Code Review
  - Collaboration
  - Agile Teams
categories: []
draft: false
---
In the world of software development, the practice of code reviews not only assures the quality of code but also fosters collaboration, mentorship, and knowledge sharing. However, if not optimised, code reviews can become time-consuming, demoralising, and inefficient. Here are some tips to help with optimising reviews.

### **Tip #1: The Importance of Self-Review Before Submitting Code Changes**

In the dynamic world of software development, maintaining code quality is paramount. It’s not just about writing code that works. It’s about writing code that’s clean, maintainable, and efficient. This is where the practice of self-review comes into play.

Why Self-Review?

Before you hit the Submit button on your pull request or merge request, take a moment. Dive back into your code. A self-review is more than just a cursory glance. It’s a deep dive into your own work, ensuring that you’ve not only met the functional requirements but also upheld the standards of code quality. This proactive approach not only helps in catching potential issues early but also instills a sense of responsibility and pride in one’s work.

***Best practices* —** Developers can use eslint or sonar lint to fix the issues from their end.

### **Tip #2: Establish Clear Guidelines and Standards**

Draft a code review guide that sets expectations for both authors and reviewers. This can include coding standards, styles, and common pitfalls to look out for. Encourage authors to provide relevant context. This can be a brief description, related ticket numbers, or design documents.

***Best practices***

**Naming Conventions:** Consistent and descriptive names for variables, functions, classes, and other code elements.

![](/article/code-1.png)

**Code Formatting:** Consistent indentation, spacing, and line length for improved readability.

![](/article/code-2.png)

**Documentation:** Clear and concise comments and documentation to explain the purpose, functionality, and usage of code.

![](/article/code-3.png)

Expected output

![](/article/code-4.png)

**Error Handling:** Appropriate handling of exceptions and error conditions to ensure robustness and maintainability.

![](/article/code-5.png)

Expected output

![](/article/code-6.png)

**Code Modularity:** Breaking down code into modular components or functions for reusability and easier maintenance.

validation.js file

![](/article/code-7.png)

api.js file

![](/article/code-8.png)

user.js file

![](/article/code-9.png)

index.js

![](/article/code-10.png)

**Code Efficiency:** Encouraging the reuse of existing code or libraries to reduce duplication and promote efficiency. There are principles that we can follow. 

**DRY (Don’t repeat yourself)**

The DRY principle, abbreviated for “Don’t Repeat Yourself,” underscores the significance of crafting code that’s both modular and reusable, thereby eliminating redundancy. By adhering to the DRY principle, developers ensure that every segment of code has a distinct, singular function, allowing it to be seamlessly integrated across various parts of an application without necessitating repetition. This approach not only streamlines development but also enhances maintainability, as changes made to a singular, reused piece of code propagate throughout the application, ensuring consistency and reducing potential errors.

Here are some tips to follow when implementing the DRY principle:

* Use functions to encapsulate reusable code.
* Extract common functionality into separate modules.
* Use variables to store repeated values.
* Avoid copying and pasting code.

![](/article/code-11.png)

The **KISS** principle, an acronym for “**Keep It Simple, Stupid**,” advocates for simplicity in code design. By adhering to the KISS principle, developers prioritise clarity and comprehensibility, ensuring that the code remains accessible and maintainable. This not only facilitates smoother collaboration but also minimises the risk of errors.

To effectively implement the KISS principle:

* Craft straightforward and intuitive code.
* Opt for self-explanatory variable and function names.
* Decompose intricate problems into more manageable sub-tasks.
* Resist the urge to overcomplicate solutions.

For instance, when developing a function with a designated purpose, it’s crucial to ensure its logic remains unambiguous and devoid of superfluous intricacies.

![](/article/code-12.png)

**YAGNI: You Ain’t Gonna Need It**

YAGNI, an acronym for “You Ain’t Gonna Need It,” underscores the significance of avoiding superfluous features in your code. By adhering to the YAGNI principle, developers can concentrate on the present requirements, ensuring efficient use of time and resources without overburdening the application.

To effectively embrace the YAGNI principle:

* Prioritise immediate requirements, coding only what’s essential.
* Resist the temptation to introduce features without a current need.
* Adapt and refactor code as new necessities emerge.
* Refrain from over-anticipating future scenarios or functionalities.

![](/article/code-13.png)

**Testing:** Incorporating unit tests or automated testing practices to ensure code correctness and reliability.

**Unit testing**

A software testing technique where individual units or components of a software are tested in isolation from the rest of the application. The primary goal is to validate that each unit of the software performs as designed.

Importance of Unit Testing:

* Quality Assurance: Ensures that individual parts of the code work correctly.
* Early Bug Detection: Helps in catching bugs early in the development cycle, preventing potential issues in later stages.
* Refactoring Safety: When making changes or refactoring, unit tests can ensure that the functionality remains intact.
* Improved Design: Writing tests often leads to better code design and modularity since it’s easier to test smaller, well-defined functions.
* Documentation: Unit tests serve as documentation by example, showing how a piece of functionality is expected to behave.
* Continuous Integration: Unit tests can be automated and run every time code is pushed to a repository, ensuring that new changes don’t introduce regressions.

Example -

calculateRectangleArea.js

![](/article/code-14.png)

calculateArea.spec.js

![](/article/code-15.png)

**Security:** Adhering to secure coding practices, such as input validation, proper authentication and authorization mechanisms, and data encryption.

![](/article/code-16.png)

### **Tip #3: Time-Box Code Reviews**

Time-boxing code reviews can be an effective strategy to streamline the development process and ensure consistent code quality. By allocating specific times during the day solely for reviewing code, developers can prevent the review process from becoming an overwhelming task that hinders their productivity. This structured approach not only helps in maintaining the momentum of development but also ensures that code reviews are given the attention they deserve.

Moreover, it’s crucial to avoid protracted reviews. If a review session seems to be dragging on, it might be more beneficial to break it down into more manageable parts or even opt for a face-to-face discussion. This ensures that feedback is clear, concise, and actionable, leading to more efficient code integration and collaboration.

***Best Practices —*** The reviewer will consider the priority-based features or bugs, and review the pull request and merge them. From a developer point of view, they need to add the proper bug id or feature they are developing.

### **Tip #4: Encourage Peer Review System**

Encouraging a peer review system within a development team can significantly enhance the quality and robustness of the codebase. Different developers, with their unique experiences and perspectives, can identify a range of issues that might be overlooked by a single individual. This diversity not only aids in catching distinct problems but also fosters a sense of shared code ownership, promoting collective responsibility for the code’s quality.

Furthermore, rotating reviewers is a strategic move to prevent any single member from experiencing review fatigue. This rotation also serves as a platform for knowledge sharing, ensuring that team members are continually learning from one another and that expertise is evenly distributed throughout the team.

***Best practices —*** Assign more than one developer to review the code changes. In case one misses something, the other can catch it, saving more time. At the same time, they are able to provide different approaches for the problem.

### **Tip #5: Communication — A Pillar of Effective Reviews**

Beyond the lines of code lies the pivotal realm of human interaction.

Constructive Feedback Culture: A constructive feedback culture is pivotal in fostering a collaborative and growth-oriented environment. By anchoring feedback in positivity, reviewers can encourage open dialogue and mutual respect. Utilising phrases such as “Consider changing…” or “What are your thoughts on…” not only softens the delivery but also invites a two-way conversation, allowing the recipient to feel valued and understood. Such an approach stands in stark contrast to direct criticism, which can often come across as confrontational or dismissive. By choosing words that uplift rather than deflate, teams can ensure that feedback becomes a tool for enhancement and learning rather than a source of contention or defensiveness.

Face-to-Face for Complexity: For intricate discussions or sensitive feedback, in-person or video interactions can prove invaluable, preventing misinterpretations that textual feedback might induce.

**Best Practices —** If there are any issues or modifications, the reviewer must tell the assignee in a more polite way like “Please add ….”

### **Tip #6: Open-Source Tools for Code Reviews**

* [Gerrit](https://www.gerritcodereview.com/): A web-based code review system for Git repositories.
* [Phabricator](https://www.phacility.com/phabricator/): A suite of web-based tools for code review, version control, and project management.
* [Review Board](https://www.reviewboard.org/): A web-based collaborative code review tool.
* [RuboCop](https://docs.rubocop.org/rubocop/automated_code_review.html): A Ruby static code analyzer and formatter.
* [Checkstyle](https://checkstyle.sourceforge.io/): A tool for checking Java code against a set of defined coding standards.

In wrapping up, the essence of optimising code reviews pivots on a blend of clear guidelines, advanced tooling, human-centric communication, and a commitment to continuous improvement. With these strategies, teams can elevate their code review practices, ensuring both efficient and robust software delivery.