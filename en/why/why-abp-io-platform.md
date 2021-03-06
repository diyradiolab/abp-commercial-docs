# Why ABP.IO Platform?

This document aims to answer to the big question:

> "Why should you use the ABP.IO Platform instead of creating a new solution from scratch?"

The document introduces the challenges of building a modern software solution and explains how ABP addresses these challenges.

## Creating a New Solution

When you need to start a new solution, there are **a lot of questions** you need to ask yourself and you should spend **a lot of time** before starting to write your **very first business code**.

### Creating an Empty Solution

Even creating an almost-empty solution is challenging;

*   How do you **organize your codebase** across projects?
*   What are the **layers** and how they interact with each other?
*   How do you **integrate** to 3rd-party library and systems?
*   How to setup the automated **tests**?

ABP provides a **well-architected**, **layered** and **production-ready** [startup solution](https://docs.abp.io/en/abp/latest/Startup-Templates/Application) based on the [Domain Driven Design](https://docs.abp.io/en/abp/latest/Domain-Driven-Design) principles. The solution also includes a pre-configured **unit** and **integration** [test](https://docs.abp.io/en/abp/latest/Testing) projects for each layer.

Creating such a solution structure requires a good **architectural experience** and a **significant time to prepare** it. ABP provides it in just one minute.

### Common Libraries

Which **libraries** you should use to implement for **common requirements**? Software development ecosystem is highly dynamic and it is **hard to follow** the latest tools, libraries, trends and approaches.

ABP **pre-integrates** the **popular**, **mature** and **up to date libraries** into the solution. You don't spend your time to integrate them and talking to each other. They properly work out of the box.

### UI Theme & Layout

When it comes to the UI, there are a lot of challenges including to prepare a foundation to create a **responsive**, **modern** and **flexible** UI kit with a consistent look & feel and tons of features (like left/top navigation menu, header, toolbar, footer, widgets... etc).

Even if you buy a pre-built theme, **integrating** it to your solution may take **days of development**. Upgrading such a theme is another problem. Most of the times, the theme's HTML/CSS structure is mixed to your UI code and it is not easy to **upgrade** or **change** the theme later.

ABP Framework provides a [theming](https://docs.abp.io/en/abp/latest/UI/AspNetCore/Theming) system that makes your UI code independent from the theme. Themes are isolated and they are **NuGet/NPM packages**. Installing or upgrading a theme is just a minute. While you can build your own theme (or integrate an existing theme), ABP Commercial offers **professional and modern** [themes](https://commercial.abp.io/themes).

> There are also UI **component providers** (like Telerik and DevExpress). But they only provide individual components. You are the responsible to create your own **layout system**. You **can use** such libraries in your ABP based solutions just like using in any other project.

### Coding Standards & Training

Once you create the solution that is ready for development, you typically need to **train the developers** to make them understand the system and develop it with the same **conventions** in a **standard** and consistent way. Even if you train the developers, it is **hard to prepare and maintain a documentation** to explain how to make the development. So, by the time, every developer will write the code in a different style and coding standards will begin to diverge.

ABP solution is already **well-defined** and **well-documented**. [Tutorials](https://docs.abp.io/en/abp/latest/Tutorials/Part-1) and [best practice guides](https://docs.abp.io/en/abp/latest/Best-Practices/Index) clearly explain how to make development on this solution.

## Don't Repeat Yourself!

Creating a base solution takes a significant amount of time and requires a good architectural experience. However, this is just the beginning! As you start developing, you will find that you have to write lots of repetitive code that would be great if all this could be handled automatically.

### Cross-Cutting Concerns

Cross-Cutting Concerns are the fundamental repeating logic that should be implemented for each use case. Some examples;

*   Starting **transactions**, committing on success and rollback on errors.
*   **Handling and reporting exceptions**, returning a proper error response to the clients. Handling error cases in the client-side.
*   Implementing **authorization** and **validation**, returning proper responses and handling these in the client-side.
*   TODO: MORE

ABP Framework automates or simplifies all the standard cross-cutting concerns. You only write code that matters for your business and ABP handles the rest by conventions.

### Architectural Infrastructure

You typically need to build **infrastructure** to properly implement your **architecture**. For example, you generally implement some kind of the **Repository** pattern. You define some **base classes** to **simplify** and **standardize** to create entities, services, controllers and other kinds of objects.

ABP Framework provides all these and more out of the box. It is mature and well documented.

### Enterprise Application Requirements

There are a lot of requirements you repeatedly implement in every business application;

* Detailed **permission system** and managing permissions on the UI based on roles and users.
* Writing **audit logs** and **entity histories** to track when an entity is changed by a user.
* Making your entities ***soft delete***, so they are marked as deleted instead of really deleting from the database and automatically filtering deleted entities on your queries.
* Creating abstractions and wrappers to **consume your backend APIs** from the frontend code.
* Enqueuing and executing **background jobs**.
* Handling multiple **time zones** in a global system.

There are a lot of more. ABP provides infrastructure to implement such requirements easily. Again, you don't spend your valuable time to re-implement all these again and again.

### Integrating to 3rd-Party Libraries and Systems

Most of the libraries are designed as **low level** and you typically do some amount of work to properly integrate them **without repeating** the same integration and configuration code everywhere in your solution.

For example assume that you need to use **RabbitMQ** as a distributed event bus. All you want to send a message to a queue and handle the messages with some code in your solution. But you need to understand **messaging patterns**, queue and **exchange details**. If you want to write an efficient code, you need to create a **pool** to manage connections, client and channels. You need to deal with **exceptions**, ACK messages, **re-connecting** to RabbitMQ on failures and more.

ABP's RabbitMQ Distributed Event Bus integration abstracts all these details. You just send and receive messages. You need to write low level code? No problem, you can always do. ABP doesn't restrict you when you need to use low level features of the library you are using.

### Why Not Build Your Own Framework?

All these infrastructure, even in the most simple way, takes a lot of time to **build**, **maintain** and **document**. It gets bigger by the time and becomes hard to maintain it in your solution. Separating these into a reusable project is the starting point to build your own **internal framework**.

Building, documenting, training and maintaining an internal framework is really hard. If you don't have a large dedicated framework team, your internal framework rapidly turns into an undocumented legacy code that no one can understand and maintain anymore.

## Modularity

Building a true modular system is not easy. All the aspects of the system (database, entities, APIs, UI pages/components) can be splitted into modules and each module can be reusable without others. Plain ASP.NET Core doesn't provide such a modular architecture. If you need it, you should think on it from scratch.

ABP Framework is designed to build modular applications and systems. Every feature in the framework is developed so it is compatible with the modularity. Documentation and guides explain how to develop reusable modules in a standard way.

## Microservice Architecture

TODO