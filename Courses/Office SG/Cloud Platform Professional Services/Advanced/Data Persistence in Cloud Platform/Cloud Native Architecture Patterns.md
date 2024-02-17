# Cloud Native Architecture Patterns

## Cloud native application definition

* Reminder of the promises of the Cloud
    * The benefits of the Cloud are organized around 4 main themes
        * Elasticity
            * The Cloud allows infrastructure resources to be automatically adapted to actual needs (e.g.. increasing processing capacity for end-of-month regulatory reporting). The capabilities of a Cloud seen for an application are 'almost infinite'
        * Agility
            * The Cloud makes it possible to reduce time-to-market through the ability to create or stop technical environments to run applications in minutes
        * Innovation
            * The richness of Cloud providers' catalogs, especially in terms of data science. Artificial intelligence and low-cost pre-packaged sandboxes, allows to accelerate the development of new use cases
        * Cost on demand
            * The Cloud makes it possible to pay only for what is actually used, to adapt infrastructure to real-time needs, to avoid heavy new investments (in particular to absorb load peaks over a short period of time or for deployment of international use cases)
    * To advantage of these benefits your application must be Cloud native

* Definition of a Cloud Native application
    * A Cloud native application is a distributed, elastic and scalable system
    * Cloud native applications are a composition of various services (applications core, storage, network, authentication, monitoring, orchestration, etc.). These services integrate small components carrying a single process (microservice) - autonomous, stateless and weakly coupled - designed to be scalable. Perennial data is isolated in a so-called persistence zone
    * The microservice communicate with each other being agnostic of the languages used
    * One of the main objectives of a Cloud native application is to use its underlying resources as economically as possible
    * The deployment of a Cloud native application is automated, at each stage and performs technical and functional tests before going into production (CI / CD pipeline)
    * It is of course possible to run an application in the Cloud that does not meet all these criteria. In this case, it would be described as a 'Cloud Hosted' or 'Cloud Ready' application instead of Cloud native and then, would not be able to obtain all the benefits of the Cloud

* Cloud native application
    * Key characteristics of a Cloud native application (CNA)
        * Infrastructure independent
        * Service-oriented architecture (SOA)
        * Cost and resource consumption aware
        * Location independent
        * Elastically scalable
        * Bandwidth aware
        * Resilient to failure
        * Designed for manageability
        * Secure
    * In order to get the key characteristics of a CNA, the following principles have to be applied
        * API programming
        * Micro-services-oriented architecture (a service should do one thing well)
        * Stateless services
        * Cloud native architecture design pattern 12-Factor application
        * Infrastructure as code

## API programming and microservices

* A Cloud Native application exposes the API of each of its services. Calling a given service API triggers asynchronous communications between its microservices which perform tasks
    * Monolithic application
    * Modules based application
    * Services based application

* Microservices
    * Microservices oriented architecture is
        * Evolving
            * Deployment of functionalities without downtime via CI / CD and versioning management
            * Interoperability of different technologies or development languages in teh same application
        * Modular
            * Each functionality is autonomous, independent, resilient, scalable and elastic
        * Agile
            * Application lifecycle by functionality
            * Lightweight communications mechanisms in asynchronous mode (API)
    * To build an application based on microservices
        * As a input, a stable interface contract must be published. This allows to be autonomous and independent to develop and bring evolutions
        * The output formats must be published so that the next function can evolve in total autonomy
            * There cant be processing without output

* Component type : stateful vs stateless
    * Stateful
        * A stateful component stores certain data that will be required for further processing
        * For a stateful application, the persistence area is stored locally
    * Stateless
        * A stateless component does not store any data that needs to be kept longer than the transaction time
        * The processing of a transaction will follow the following scenario
            * Identification of information issued by the customer
            * Retrieving additional information in an area external to the component, the 'persistence area'
            * Performing processing
            * Provision of the result for further processing
            * Context cleaning (especially for data confidentiality)

* Stateful
    * Advantages
        * As the data is stored locally, processing is often faster what with a Stateless architecture
    * Disadvantages
        * In case of interruption of a session, you must have implemented audit trails of fines in order to be able to carry out a recovery (this point is linked to the context at the time of the interruption which is probably different from the initial context)
        * If the component is lost, the data is lost. Often complex mechanisms must therefore be implemented to overcome this
        * If the component is duplicated to bring power, it will be necessary to implement data sharing solutions to ensure consistency

* Stateless
    * Advantages
        * Each transaction is independent, it has no link with the previous or next transaction. This allows the implementation of the 'elasticity' of these components without any prior modification
    * Disadvantages
        * The treatments are often slightly longer than with a stateful architecture because there can be consultation of external information

## The 12 Factor Application

* The origin of the 12-Factor App concept
    * In today's era, software is regularly delivered as a service :  the terms web applications (software apps) or software as a service are often used
    * The 12-Factor App is a methodology for designing software as a service that
        * Take advantage of automation to reduce the time and cost of implementing any new service
        * Provide maximum portability between runtime environments
        * Are decoupled from infrastructure to reduce administration tasks for the underlying systems and improve fault tolerance
        * Minimize the gap between development and production, allowing continuous deployment for maximum agility
        * And can grow (scalability) without significant change in tools, architecture, or development practices
    * The 12-Factor application methodology can be applied to applications written in any programming language, and which use any type of external service (database, message, authentication, etc.)

* What are the 12 factors
    * Codebase : One codebase tracked in revision control, many deploys
        * A version control system
        * A code repository
        * Code base isolation per application
        * Invoicing of 'reusable' code transversally in another code base
    * Dependencies : Explicitly declare and isolate dependencies
        * Explicitly declare and isolate Dependencies
        * No implicit dependency
        * All code useful to the application (no exceptions) must be contained in the deployment package
    * Config : Store config in the environment
        * Separate the code from the configuration
    * Backing services : Treat backing services as attached resources
        * Treat backing services as attached resources
    * Build, release, run : Strictly separate build and run stages
        *  Strictly separate build and run stages
    * Processes : Execute the app as one or more stateless processes
        * Run the application as one or more stateless process
        * Each process must be autonomous
        * A process stores its data in a persistent service between each operation
        * Information exchanges between processes are carried out using persistent services
    * Port binding : Export service via port binding
    * Concurrency : Scale out via the process model
    * Disposability : Maximize robustness with fast startup and graceful shutdown
    * Dev / prod parity : Keep development, staging and production as similar as possible
    * Logs : Treat logs as event streams
    * Admin processes : Run admin / management tasks as one-off processes