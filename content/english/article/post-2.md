---
title: "The guardian angels of your code"
description: "software testing using xUnit"
image: /article/post-2-banner.png
date: 2021-06-22T11:33:57+06:00
author: "Insighture Technology"
tags:
  - Software Testing
  - xUnit
categories:
  - Software Development
draft: false
---

**Target Audience: Developers**

**Introduction**

In any software development life cycle, software testing plays a major
role in ensuring the given application meets the expected business
objects as defined. This can be in the form of UI/UX, API,
Business/Functionality, Security or Performance aspects. Moreover, this
can be further divided into automation and manual testing. Usually,
functional, smoke, regression and release testing are performed by field
expertise in QA or Staging environments and there is a controversy on
feasibility of conducting end-to-end testing each and every release to
ensure nothing is broken from previous to current release.

I strongly believe as developers, it is our responsibility to release a
fully tested stable (not only just the feature but also the existing
functionality) source code to QA environments to minimize the back and
forth iterations. Eventually, it will increase the throughput of the
project development life cycle.

Unit Testing plays a major role in ensuring individual modules/business
rules are tested and validated in all aspects by the developer to
determine whether they are fit for use prior to any releasing
activities.

**Vision & Goal**

In this series of articles on Unit Testing (using xUnit Framework), I
will be covering the following sections as in multiple articles to
minimize the reading overhead and build up as in a step by step guide.

1.&nbsp;Unit Testing \[Part 1\]: Use of In-Memory database & mock with
  > Builder Pattern - Service Layer Testing

2.&nbsp;Unit Testing \[Part 2\]: Testing API Endpoints & contracts

3.&nbsp;Unit Testing \[Part 3\]: Generate Code Coverage Reports

4.&nbsp;Unit Testing \[Part 4\]: Integrate Code Coverage into
  > Azure Build Pipeline.

Ultimate goal of the above articles is to increase the quality of the
code and practice writing unit tests in all the projects regardless of
the scale of the software.

**Expected Ratio**

-   Service Layer: 100%

-   API Layer : at least 80%

-   Integration Endpoints: at least 80%

-   Front end: above 60%

For illustration purposes, I have created the following class
libraries/Api projects along with the below npm packages.

![](/article/post-2-image8.png)

**DemoApp.Services.Tests**

-   FluentAssertions

-   Microsoft.EntityFrameworkCore.InMemory

-   Moq

-   xunit

-   Xunit.runner.visualstudio

**DemoApp.Services**

-   Microsoft.EntityFrameworkCore

**DemoApp.Domain.Models / DemoApp.Domain.Entities**

-   N/A

**DemoApp.API**

-   Swashbuckle.AspNetCore

**Quick look on Builder Pattern**

GOF (Gang of Four) says:

> *"Separate the construction of a complex object from its
> representation so that the same construction process can create
> different representations"*

The Builder Pattern is a creational design pattern which is used to
build a complex object by using a step by step approach. Moreover,
extract the object construction code out of its own class and put it in
a separate object which we call a builder and this class is responsible
for creating an instance of a specific object.

**What is a Fixture**

When executing a set of Test Cases, we will need to set up a common data
set throughout the test execution depending on the scope of the Tests.
Sometimes, we might need to set up fresh data in each and every test
case, sometimes just one single shared context per test class. Concept
of Test Fixture comes in handy to streamline the test data preparation.
xUnit has provided following:

1.&nbsp;**Constructor and Dispose**: Use case of cleaning the test context for each and every test without sharing the object instance. Also known as
  > "***Test Class as Context***"

2.&nbsp;**Class Fixture:** Use case of sharing the same object instance across tests within a single class.

3.&nbsp;**Collection Fixture:** Use case of sharing the same instance across multiple test classes.  
<br/><br/>
Let's go through the code snippet and understand the what we are going to do here:
<br/><br/>
**Service Layer Unit Testing: Use of In-Memory databases & mock with
Builder Pattern**

Note: You will notice a few additional code snippets on Soft Deletion,
use of auditable entities and accessing request context values to make a
demo application almost similar to production scenario.

If you don't want a hard deletion, you may introduce the ISoftDelete
interface and implement it in relevant entities.

![](/article/post-2-image14.png)

Purpose of an Auditable Entity is to track who has executed the action
against the data record. We can set all the relevant values inside the
DataContext. I have injected IUserContext to extract user information
from the HttpContext.

![](/article/post-2-image12.png)

I will discuss the implementation of IUserContext in the API testing
section.

![](/article/post-2-image21.png)

Now, let's have a look at User Entity which has implemented ISoftDelete
and IAuditableEnttity. I have also added a parameterized constructor to
support UserBuilder Class in UnitTesting.

![](/article/post-2-image17.png)

One of the most important parts of Application setup is Creating the
Datacontext. I have used EF Core DbContext default behavior and have
overridden the SaveChanagesAsync() method. All the entities which have
implemented IAuditableEntity, can set values as follows. The key benefit
of this approach is to reduce the duplication of handling auditable
fields in all the entities. In this way, you can centralize the behavior
of the Auditable in a more robust way.

![](/article/post-2-image9.png)

Let's use the builder pattern to create a UserBuilder class. This will
contain all or few properties that we are gonna use for Unit Testing,
basically the fields that are required for business flow verifications.

Following the naming convention as I have used in the below class which
will provide a concise use of the fields in Test Classes.

![](/article/post-2-image16.png)

One last thing before jumping to Unit Test Project is to set up a class
Fixture. Ultimate goal of this class is to share the TestDataContext
throughout the same class test execution.

![](/article/post-2-image5.png)

We have come to the last part of this article on writing Unit Tests for
User Class. All the set up activities are supportive classes/methods to
write more meaningful cases to cover the business logic aspects of the
service layer.

**Note:** Readup more on xUnit and understand **Fact**, **InlineData**,
**Theory** concepts and apply it depending on your testing scenario.

Here are some test cases that I have picked randomly to showcase Unit
Testing scenarios. There are dozens of naming conventions out there,
however I'd prefer following

1.&nbsp;MethodName_StateUnderTest_ExpectedBehavior

2.&nbsp;Should_ExpectedBehavior_When_StateUnderTest

**Test Case 01: Application should not allow Email duplicates**

![](/article/post-2-image22.png)

**Test Case 02: Application should allow inserting a user with a new
email address and return the inserted Id.**

![](/article/post-2-image13.png)

**Test Case 03: Deleting an existing user with a given email should
return true or false**

![](/article/post-2-image18.png)

**Test Case 04: Deleting a non-existing user with a given email should
throw**

![](/article/post-2-image19.png)

**Test Case 05: Should return User details for the given existing User
Id**

![](/article/post-2-image15.png)

**Test class constructor**

![](/article/post-2-image20.png)

**Testing an Extension method with Theory** and **InlineData**

I have created a simple extension method to validate the email address
using Regex.

![](/article/post-2-image7.png)

![](/article/post-2-image11.png)

**Test Results**

![](/article/post-2-image10.png)

---

*This is the end of Unit Testing Part 1*

---
