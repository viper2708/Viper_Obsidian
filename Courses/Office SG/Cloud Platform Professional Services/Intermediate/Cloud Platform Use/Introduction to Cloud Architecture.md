## What is the Cloud? What are the different types of Cloud?

* What is the Cloud exactly?
    * The Cloud (Computing) is a way of providing access to computer resources, characterized by its self-service availability, elasticity, openness, mutualisation and pay-per-use
        * Self-service and on-demand resources of storage capacity and computing power, according to the customer's needs. This contrasts with so-called "traditional" computing where any need to change an application requires manual operations and therefore time.In the Cloud, the need, automatically detected by the application or at the customer's request, is taken into account and satisfied immediately.
        * Openness : Cloud services are accessible through a network, using standardized techniques, whether from a computer, a amartphone or a tablet
        * Mutualization : The Cloud mutualizes its IT resources (servers, CPU, RAM, storage, network) to serve its customers, to whom the ordered resources are allocated according to automatic processes. Mutualization improves scalability and elasticity; it facilitates the automatic adaptation of resources to variations in demand
        * Pay-per-use: The quantity of services consumed in the Cloud is measured for purposes of control, adaptation of technical means and billing.

* With the Cloud, we should talk about "XAAS". What's XAAS?
    * The acronym XaaS refers to Everything-as-a-Service. This term refers to the different models of Cloud computing "as a service"
    * Indeed with the Cloud, we no longer speak of infrastructure components but of services, which explains the syntax of the terms (aaS). XaaS services are organised into 3 categories
        * IaaS (Infrastructure as a Service) : Provides CPU, storage, RAM, Network
        * PaaS (Platform as a Service) : Provides ready-to-use middlewares (database, web server,etc.)
        * SaaS (Software as a Service) : Provides ready-to-use softwares (CRM, expense claim management, online office automation tools such as Office 365, payroll management, etc.)
    * We talk about "Infrastructure as a Service" is the case where:
        * The client manages the middlewares and softwares (executables, settings, databases)
        * The Cloud provider manages server hardware, virtualization layers, storage, networks
    * It is a model where the customer has, on a paying subscription basis, an IT infrastructure (servers, storage, backup, network) that is physically located at the Cloud provider

* XaaS service in detail
    * Infrastructure as a Service (IaaS)
        * It's the lowest level of service. It consist of providing access to a virtualized computer park. Virtual machines on which the customer can install an operating system and applications. The service is similar to traditional data center hosting services, and the trend is towards highest level services (PaaS or IaaS) that are more abstract in terms of technical details
    * Platform as a Service
        * In this type of service, the operating system and infrastructure tools are the responsibility of the Cloud provider. The customer has direct access to specialized services (web front-ends, middlewares, databases, etc.) that can be customized: the customer chooses, in a Marketplace, the design of the technical solution to be deployed. The Cloud provider will execute the implementation with its own Scripts.
        * Advantage
            * The customer of the Cloud solution will be able to focus on the business application to be implemented
        * Disadvantage
            * In the event that the PaaS provider decides to no longer authorize the use of a tool or a version, or to interrupt or develop its offer, the consumer must adapt within the timeframe chosen by the PaaS provider
    * Software as a Service
        * In this type of service, software are made available to clients, accessible from a Web browser or installed on a PC for rental. The customer does not have to worry about making updates, adding security patches and ensuring the availability of the service
        * Advantage
            * Rapid implementation and provision of services for the customer. No need to worry about software packagees and licenses anymore. The service is immediately 'available online'
            * As the software is managed by the provider, customers no longer need to worry about deployments, maintenance and technical evolution phases of the Service
        * Disadvantage
            * It is difficult to manage service interruptions; customers have to organize themselves around the constraints imposed by the SaaS provider
            * It is necessary to comply with the supplier's prerequisites for a good use
            * The customer is subject to the SaaS product product lifecycle by the Cloud provider, particularly in the event of a lack orabandonment of functionality
    * A SaaS provider can operate PaaS-type services, which in turn can use IaaS.
    * The use of services (IaaS-PaaS-SaaS), by its nature, is therefore a shared responsibility.

* The different types of clouds
    * The public cloud
        * The infrastructure is mutualized ans is shared between several companies and individuals. It is owned by a service provider. The Service Level Agreement (SLA) is the same for all users and is defined by the provider
            * Natively, Public Cloud services are provided in a virtualized environment, built using physical resources in pools shared with all other subscribers
        * The services are accessible via the Internet
        * The Public Cloud offers the following features and benefits
            * High resource scalability so that an application can respond flexibly to charge fluctuations
            * Only leased resources are billed
            * The pricing model is based on what is consumed(no cost on unused resources)
        * No more need to tie up resources to anticipate future needs
            * The (very) high availability of access to environments
        * The multitude of physical components implemented by the supplier to create a Public Cloud means that there is no (theoretically) infrastructure SPOF (Single Point of Failure : a system-part whose failure stops the system from working)
            * The services offered can meet most of the requirements and use cases sought by the company
            * Customers have access to a standardized environment
    * The Private Cloud
        * It is an environment exclusively used by a company
        * The company is then responsible for the purchase, installation and management of servers, network, storage, etc. all of which are protected by security solutions implemented by the company
        * The Private Cloud can be hosted in company-owned datacenter or hosted by a partner
    * The Hybrid Cloud
        * It is a use of several Clouds where all combinations between Private and Public Clouds are possible
        * These combinations of several types of accomodation totally independent of each other require to respect:
            * Technological standards to be able to communicate between Clouds
            * A network connectivity that can meet the needs
        * The Hybrid Cloud makes it possible to shift workloads between different types of hosting according to changing needs, cost reduction or in case of need for dynamic increase of mass resources

* The Cloud Market
    * According to the RightScale (2019) report on the state of cloud computing, 91% of companies reported using a Public Cloud service
    * Gartner's most recent data on the global market for infrastructure as Cloud IaaS Service indicates annual revenues of 32.4 billion dollars. This is a 31.3% growth from 24.7 billion dollars in 2017.
    * According to Gartner, the market is dominated by 5 vendors that account for nearly 80% of the global Cloud IaaS market share in 2018
        * AWS : 50%
        * Microsoft Azure : 15%
        * Alibaba Cloud : 8%
        * Google Cloud Platform : 5%
        * IBM Cloud :2%

## What are the key architecture concepts of the Cloud?

* Anatomy of the Cloud
    * A Cloud is made up of regions, which in turn are made up of Availability Zones(AZs) that contain services
        * Region :
            * It is a collection of availability zones. The regions are far enough apart from each other so that they are not simultaneously impacted by disasters of regional scope: earthquake, electrical grid loss, etc. The regions are too far apart to allow synchronoud data replication
        * Availability Zones :
            * This is a deployment zone for infrastructure resources that can be deployed via the Cloud. Zones in the same region are close enough to be interconnected with high-capacity, low-latency network links that allow synchronous data replication. However they are far enough apart to avoid being impacted by local disasters such as loss of power, fire, etc. A distance of a few km to 50 km is generally observed
        * Services
            * As seen in the previous section, a cloud is composed of automated services
    * These services can be classified into two categories:
        * Services that support the operation of the Cloud
            * Billing
            * Supervision
            * Events
            * Authorizations
        * Infrastructure services
            * VM
            * Containers
            * Load Balancer
            * Databases

* Anatomy of a Cloud: how it works
    * Consumers of Cloud Platform
        * Developers
        * Applications
        * COO, etc.
    * There are several ways to interact with a service
        * By API
        * On the command line (CLI)
        * By a console (DoItNow internally)
    * Cloud Platform is composed of unit services called XaaS
    * A resource can be any infrastructure object that supports an application (examples: VM, database, VIP, DNA aliases, etc.)
    * Control plane
        * Everything that allows you to manage the service's resources (creation, deletion, supervision, etc.)
    * Resource plane
        * These are the resources created by the service (VMs, databases, etc.)

* Some key concepts - the account at the heart of everything
    * The Clouds are organized around the notion of account. This account can be seen as a container for all the resources deployed within a Cloud : database, virtual machines, etc.
    * The same account will be used:
        * To manage the authorization on the services and resources of Cloud Platform
        * To also manage the billing of services
        * The only thing to remember at this stage is that you will need an account to access Cloud Platform. If you want to know more, please consult the specific MOOC on IAM (Identity and Access Management)

* Cloud native, what does that mean?
    * As described above, a Cloud brings a number of benefits (elasticity, agility, etc.)
    * Nevertheless, in order to take full advantage of the Cloud, applications need to be designed for it. These applications are called Cloud Native Applications : born in the Cloud
    * Multiple frameworks (eg. 12 factors) exist to define precisely what this concept is and the detailed characteristics of the applications implementing it. This will be the subject of the Level 2 MOOC

* We will summarize them here in the three main characteristics:
    * Resilient
        * The application is designed to survive the loss of a unit component, an area of availability or even a region if necessary. In the same way, an application must support temporary network modifications: throughput, latency, etc.
    * Elastic
        * The application must be able to adapt to the number of requests in order to optimize its operating cost
    * Automated
        * The application is deployed automatically through a continuous deployment chain on infrastructure components which are themselves created in an automated way (infra as code)
        * The application does not require manual actions on the unit components, metrics are fed back and automatic actions are taken on the basis of these metrics

## What does the Societe Generale cloud offer?

* What are the founding principles of Cloud Platform?
    * The Societe Generale Cloud Platform has been designed to be multi-Cloud and aligned, for its internal services, with the concepts of the Public Cloud and market standards :
        * Multi-Cloud as it offers internal services and native access to the Public Cloud in accordance with the regulator's rules and the Group's security rules
        * Aligned with Cloud concepts and market standards, it enables internal applications to be designed in the same ways as in the Public Cloud
    * The service offering has been designed to support Cloud Native Applications and DevOps / NoOps practices :
        * The service catalog therefore offers the minimum services enabling Cloud Native architectures (eg. load balancer, containers, event management, etc.)
        * And to support DevOps / NoOps practices, all services are accessible via API
    * Services are designed from the outset to be agnostic of the customer them : in concrete terms, the service consumed is the same regardless of the IT department (BSC, GBSU, ITIM, IRBS)
    * Finally, all services are attractively priced and are billed on a pay-per-use basis

* One Internal Cloud and two Public Clouds
    * Regions of presence of the GTS Private Cloud in the world :
        * USA East - 2 AZ
        * Paris - 2 AZ
        * North - 1 AZ
        * Asia - 2 AZ

* One Internal Cloud and two Public Clouds
    * Regions of presence of Public Cloud actors in the world :
        * Azure
        * AWS
    * Business lines may choose to restrict the use of the Public Cloud to certain regions

* CSP / CSP+ / MSP organization
    * Cloud Service Provider (CSP)
        * Services consumed by API, used by the customers themselves :
            * Account-centric, not application-centric (as in public CSPs)
            * Independence from uses and type of environment (everything is production)
        * Main objective
            * Openness and adaptability of the model for NoOps consumption
    * CSP+ (Controller = "Bank in compliance")
        * Business processes for Safety, Compliance, Financial Management and
        * Operations (SOC / OPM) are based on :
            * Knowledge of the application ID (communication, impact assessment)
            * Knowledge of the type of environment (prioritization, impact assessment)
        * Main objective
            * To ensure respect and compliance with enforced rules
    * Managed Service Provider (MSP)
        * Consumed services, adapted to a particular client and its ecosystem
        * Entirely used by GTS on behalf of the customer
        * Use of GTS's MSP tools
            * Marley
            * GDAT
            * iAppli
            * KAT
        * Main objective :
            * To provide managed services on customer resources

## So, Public Cloud or Private Cloud?

* What are the main criteria for choosing between Private Cloud and Public Cloud?
    * Data security
        * An application cannot be hosted in the Public Cloud if its data meets at least one of the following criteria :
            * The data is C3 (according to the critically scale C0 / C1 / C2 / C3 in force at Sociate Generale)
            * The data is subject to regulatory (eg. European Central Bank) or legal constraints
            * The data relates to private information (RGPD constraints for the protection of personal data)
            * The strategy of the Business Line, owner of the data, refuses to host it in the Public Cloud (residual risks too high estimated by the Business Line)
    * Innovation / Technological advantage
        * The richness of the catalogues of Public Cloud providers in terms of Data-Science and Artificial Intelligence can help accelerate the development of new cases planned within the different business lines (new services, fight against fraud, improvement of operational efficiency, etc.)
    * Elasticity and agility
        * Users appear to have almost unlimited resources in the Public Cloud. As a result, the Public Cloud is often better suited to large workloads or highly fluctuating demands
    * Business value vs cost
        * A comparative financial analysis (Business Case) is often necessary to make a choice. The Business Case must evaluate the value brought to the business for each type of Cloud and its operating cost (Run). The public Cloud can be penalized by telecom expenses (access to the Cloud) and by costs related to the need for reversibility management