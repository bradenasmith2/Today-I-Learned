### Dependency Injection in an ASP.NET Core App

# So, What is Dependency Injection(DI)? 

DI is a technique for providing the dependencies (objects, methods, or services) that a class needs from the outside rather than creating them internally. 
I like to think of it as a way to modularize applications even further then just inheritance or interfaces. DI can be used to separate the logic from the structure, in other words, you can create logic
in the classes, and easily manipulate what data is injected (sent) to the class. With this, it allows us to untangle objects from logic as DI sends objects into classes, rather than creating the objects in the class.


# What Are Some Benefits?

For a brief overview, DI allows for improved testability, maintainability, flexibility, and code organization. It helps create more modular, scalable, and robust applications
Specifically speaking, I learned that by injecting dependencies rather than creating them internally, it becomes much easier to substitute real dependencies with mock(test) objects during unit testing. 
This allows for more comprehensive and reliable unit tests.

Additionally, DI allows for decoupling (separation of concerns), since a class doesn't need to know how their dependencies are created or maintained, this allows for more reusable and modular code.


# What Are Some Drawbacks?

The first and most major drawback for DI is the learning curve and complexity. Since DI highly suggests the use of interfaces and inheritance, for learning developers like me DI can be hard to implement properly, and at scale.

Secondly, when dealing with larger applications configuring and maintaining DI containers in conjunction with interfaces and inheritance can become messy very quickly. One thing that helps prevent this is careful documentation, whether external or in-app.


# Implementation

One way I have already implemented Dependency Injection is for testing. For one of my latest applications, I needed to test that my users could save their messages to my database, so without DI I would have had to create manual database connection.
However, because I'm using DI I was able to create an in-memory database each time I needed to test data being saved. At first, it may seem as though I'm just swapping real data for fake, but since I'm using In-Memory
not only does that data not leave the IDE making the test run faster, but the data is also deleted after the test to conserve resources.

Had I not used DI to perform these tests, I would have dozens of real database connections spread through several files, with each connection making the rest slower. So, because DI was implemented my tests run faster, they're more predictable and consistent,
and they are much easier to write.


### Resources on Depedency Injection in an ASP.NET Core App

This is the main .NET Depedency Injection Documentation. I found the "Multiple constructor discovery rules" section very informative.
https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection#constructor-injection-behavior

While complex, this .NET Dependency Injection Documentation provides examples on implementing DI. I found the information in "Add default implementations" helpful, and "Add interfaces" helped me understand how to combine these concepts.
https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection-usage

This site provides in-depth explanations for the different types of Dependency Injection (Constructor, Property, Method)
https://www.tutorialsteacher.com/ioc/dependency-injection