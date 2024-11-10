## What is Test-Driven Development (TDD)

* Software Development Challenges
    * Costs of developing software
        * Maintenance accounts for 65% of all software development costs.
    * Maintenance Challenges
        * Code entropy
            * Brittle over time
            * Increased rigidness
        * Isolated Ownership
            * Coder-owned silos
            * Lack of team empowerment
        * Infrequent Validation
            * Regression-prone
            * High risk of code changes
    * Legacy code
        * Source code inherited from someone else
        * Source code inherited from on older version of the software
        * Code without tests
* What is Test-Driven Development?
    * Test
        * A procedure intended to establish the quality, performance, or reliability of something, especially before it is taken into widespread use
            * Satisfies requirements
            * Responds correctly to all input
            * Acceptable performance
    * Test-Driven Development
        * A software development process that relies on the repetition of a very short development cycle : requirements are turned into very specific test cases, the the software is improved to pass the new tests, only.
        * Motto : Red-Green-Refactor
            * Red : Write test that fails
            * Green : Make test pass
            * Refactor : Refactor/cleanup code
* Why practice TDD?
    * Business benefits
        * Requirements verification
        * Regression catching
        * Lower maintenance costs
    * Developer benefits
        * Design-first
        * Avoid over-engineering
        * Momentum
        * Confidence
    * Code kata
        * Kata
            * A system of individual training exercises for practitioners of karate and other martial arts
                * Practice
                * Learning
    * Keeping focused on the customer
        * What was spec'd
        * What was delivered
        * What customer wanted

## Different ways of Testing Applications

* Types of Testing
    * Unit testing
    * Integration testing
    * Acceptance testing
* Testing styles
    * Black box testing
    * White box testing
* Testing frameworks and tools
    * xUnit frameworks
        * SUnit (Smalltalk)
            * JUnit (Java)
    * User interface frameworks
        * Selenium
        * Watir
    * System frameworks
        * Simian Army
* Testing concepts
    * Framework concepts
        * Test
            * Before Test
            * After Test
        * Test Suite
            * Before Suite
            * After Suite
    * Verification concepts
        * Assert
    * Test Execution
        * Test Runner
            * Synchronous vs Asynchronous

## Strategies and Techniques for Testing Code

* Dependency Injection
    * In software engineering, dependency injection is a technique whereby one object supplies the dependencies of another object
        * A dependency is an object that can be used
        * An injection is the passing of a dependency to a dependent object that would use it
    * Types of dependency injection
        * Constructor injection
            * Providing dependencies through a class constructor
        * Property/Setter injection
            * Using a property or setter method to inject a dependency
        * Interface injection
            * Client defines interface that describes how dependencies are injected into it.
* Test doubles
    * Test double is a "generic term for any kind of pretend object used in place of a real object for testing purposes"
    * Types of test doubles
        * Stubs : Provide canned answers to calls made during the test.
        * Mocks : Pre-programmed with expectations which form a specification.
        * Fakes
        * Spies
* Best practices
    * Treat test code like production code
        * Write readable and maintainable test code
        * Address bpth positive and negative test cases
        * Separate common set-up and teardown logic
    * Focus only on necessary values and results
        * Only assert on values required to verify the test is passing
    * Review tests and test practices with team
        * Effective techniques
        * Catching bad habits
        * Common challenges

## TDD Gotchas

* Testing anti-patterns
    * Dependencies between tests
        * Execution order of tests should not matter
        * Interdependent tests cause cascading failures and false positives
        *  Serial execution versus parallel execution
    * Testing implementation details
        * Tests should focus on the "what" not the "how"
        * Testing implementation details leads to brittle tests that break when refactoring
    * Slow-running tests
        * Prevents rapid red/green/refactor cycles
        * Warning-sign that code might be too coupled
        * Warning-sign that code might not be very testable
    * Long-running tests
        * Lower developer confidence
        * Slower release cycles
        * Less agile
* Limitations of TDD
    * Possible holes in TDD
    * TDD is not sufficient by itself
        * Deployment verification
        * Network changes
        * Integration testing
    * Management support is vital