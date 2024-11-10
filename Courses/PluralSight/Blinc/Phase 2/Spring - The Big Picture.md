## What is Spring

* 'Spring' could mean
    * The Spring Framework
    * Spring Boot
    * Spring Data
    * Spring Cloud
    * Spring Batch

* Why 'Spring'?
    * Spring started as a response to the complexity of J2EE (now Java EE)
    * Today, Spring is so much more than an alternative to Java EE
        * In fact, it's complimentary to Java EE

* Spring makes it easy to create Java enterprise applications

* Spring
    * Flexible, modular, and backwards compatible
    * Large and active community
    * Continually innovates and evolves

## Getting to Know Spring with Spring Boot

* Spring Boot notable features
    * Auto-configuration
    * Standalone
    * Opinionated

* Spring Boot Auto-configuration
    * Attempts to automatically configure your Spring application based on the dependencies that you have added
    * Auto-configurations are contextually aware and smart
    * Setting up Auto-configuration is effortless
        * Use the annotation @EnableAutoConfiguration

* Spring Boot being Standalone
    * Spring Boot makes it easy to create stand-alone, production-grade, Spring-based applications that you can 'just run'.
    * Typical process for running Java Web Applications
        * Package Application
        * Choose and Download Webserver
        * Configure Webserver
        * Deploy Application and Start Webserver
    * Spring java applications deployment
        * Package application
        * Run the application

* Spring Boot being Opinionated
    * Takes an opinionated view of building production-ready Spring applications
    * Spring Boot favors convention over configuration and is designed to get you up and running as quickly as possible

## Understanding Spring's Foundations : The Spring Framework

* Software Framework
    * Is a universal, reusable software environment that provides particular functionality as part of a larger software platform to facilitate development of software applications, products and solutions

* The Spring Framework is modular
    * Six key areas
        * Core
        * Web
        * AOP
        * Data access
        * Integration
        * Testing

* Spring Core
    * Spring Core provides a number of different features
        * i18n internalization support
        * Validation support
        * Data binding support
        * Type conversion support
    * At the center of Spring Core is Dependency Injection
        * Developers create objects to represent or model real-life things
        * Onjects don't exist by themselves
            * Objects are dependent on other objects
        * Dependency Injectionmis about dealing with the way objects fulfill their dependent objects
        * Fulfilling delendencies
            * The object fulfills its own dependencies
                * Seems easy but tightly coupled objects
            * The object declares what it depends on and something else fulfills the dependency
                * More Flexible
                * Loosely coupled objects
    * Spring Core is a dependency injection container
        * Creates and maintains objects and their dependencies
            * Less for developer to manage
        * It is the glue

* Spring Web
    * Framework for handling web requests
        * Spring Web MVC
        * Spring Web Webflux

* Spring Web MVC
    * Java Servlet
        * A servlet is an object that receives a request and generates a response based on that request
    * Challenges with the Servlet API
        * Somewhat low-level API
            * Not as easy to use
            * Less productive
    * Advantages of Spring MVC
        * Higher Level API
            * Easier to use
            * More productive
        * Clear separation of concerns
            * Model
            * View
            * Controller

* Spring Webflux
    * Reactive programming
        * A declarative programming paradigm concerned with data streams and the propagation of change
    * Spring Webflux
        * A differnt way of handling web requests
            * Asynchronous execution
            * Doesn't block (wait)
                * Better resource utilisation

* Spring AOP
    * Aspect-oriented Programming (AOP)
        * A programming paradigm that aims to increase modularity by allowing the separation of cross-cutting concerns
    * Used for
        * Used to implement features in Spring
        * A valuable tool for developers to handle cross-cutting concerns

* Spring Data Access
    * Database transactions with the Spring Framework's Data Access module are really easy
    * A database transaction is a series of database operations that must happen together or not at all
    * The Spring Framework's Data Access module also provides Exception Translation
        * Exceptions are an event within a program that disrupt execution
    * Vendor-specific exceptions are mapped into a well-known set of exceptions
    * Testing data is easier with the Spring Framework's Data Access module

* Spring Integration
    * Applications dont live in isolation
    * Integration is all about making different systems and applications work together
    * The Spring Framework makes it easier to both expose and invoke web services
    * Rest Template
        * Abstracts away tedious details
        * Handles
            * Connecting to the web service
            * Sending the command
            * Handling the response
        * RestTemplate makes calling web services as easy as one line
            * Just call the service and RestTemplate takes care of the 'rest'

* Spring Testing
    * Different ways of testing
        * Unit Testing
            * Unit Testing is a software development process in which the smallest testable parts of an application, called units, are individually and independently scrutinized for proper operation
            * Explicit support for unit testing is minimal
                * Benefits come from using dependency injection
                * Testing and dependency injection
                    * Test the smallest unit of code possible
                        * Dependencies cause challenges
                        * Dependency injection forces the developer to declare dependencies
                        * Control how dependencies behave
                            * Only test the code, not the dependencies
                            * Mock dependencies
            * Spring Framework comes with several built-in mocks to make testinf easier and faster
        * Itegration Testing
            * Integration Testing is the phase in software testing in which individual software modules are combined and tested as a group. It occures after unit testing.
            * Spring Framework provides support for piecing together parts of an application for testing
                * Inject dependencies and put everything together
            * Spring Framework provides support for common testing scenarios
                * Testing with data
                * Web application testing
            * Spring Framework provides support for cleaning up after tests
                * Tests modify things, need to reverse modifications after test so as to not affect the next tests

## Is Spring a Good Fit?

* Advantages of Spring
    * Rock solid and well engineered
    * Stood the test of time
    * Hige community
    * Well-liked
    * Large talent pool
    * Whealth of existing knowledge
    * Very actively developed
    * Built-in IDE support
    * Scalable

* Disadvantages of Spring
    * Too much 'magic'
    * Steep learning curve
    * Increase the size of your deliverable
    * Hard to debug
    * Adds memory overhead
    * Complexity has grown over time
    * Spring can be too configurable
    * Spring is 'big'
    * Spring's community projects are hit or miss