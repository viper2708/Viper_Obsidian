## The Principles of Cloud-native Architecture

* What do leading companies care about?
    * "We may not timely identify or effectively respond to consumer trends or preferences, which could negatively affect our relationship with our customers, demand for the products and services we sell, our market share and the growth of our business"
    * "We rely extensively on information systems to process transactions, summarize results and manage our business. Disruption in out systems could harm our ability to conduct our operations"
    * "If we fail to develop and maintain satisfactory relationships with physicians, hospitals and other service providers, our business could be materially and adversely affected"
    * "Our future competitiveness and ability to achieve long-term profitability depends on our ability to control our costs"

* What's expected of our software today?
    * Valued by customers
    * Constantly and easily changed
    * Available at all times
    * Scalable to meet demand
    * Secure in all respects
    * Maintainable at scale

* Defining "Cloud Native"
    * Cloud native technologies empower organizations to build and run scalable applications in modern, dynamic environments such as public, private, and hybrid clouds
    * Cloud Native is structuring teams, culture and technology to utilize automation and architectures to manage complexity and unlock velocity
    * Cloud-native is an approach to building and running applications that exploits  the advantages of the cloud computing delivery model. Cloud-native is about how applications are created and deployed, not where
    * Cloud-native software is built for scale, built for continuous change, built to tolerate failure, built for manageability

* Traits of the Cloud Native
    * Customer-centric
    * Learning culture
    * Agile developement
    * Focus on products, not projects
    * Automation of entire delivery process
    * Heavy use of open-source software

* What does positive progress look like?
    * More speed : Faster lead time, regular deployments
    * More scale : Low API response time, easily scale in and out, linear dev productivity
    * More stability : Drop in impact minutes, fast MTTR, low change failure rate
    * More secure : Fully patched software, regularly changed credentials, small amounts of unplanned work

* Cloud-native applies to more than Apps
    * Cloud-native infrastucture
    * Cloud-native data
    * Cloud-native security
    * Cloud-native integration

## The pattern of cloud-native architecture

* Application architecture pattern
    * 12-Factor applications
        * One codebase in source control
        * Declared dependencies
        * Config stored in the environment
        * Backing services as attached resources
        * Separate build and run stages
        * App executed as stataless processes
        * Services exported as port bindings
        * Scale out processes
        * Disposability
        * Environment parity
        * Treat logs like event streams
        * Run admin processes as one-off processes
    * Microservices architecture
        * Boundaries found via domain-driven design
        * Loosely coupled components
        * Continuously delivered
        * Surgical scaling
        * Contract-driven tests
        * Organized around teams
    * The supporting infrastucture for Microservices
        * Service discovery
        * Circuit breaker
        * Externalized configuration
        * Token-based security
        * Messaging
        * API gateway
    * Modern data management
        * Scalable, on-demand databases per microservice
        * Favor event sourcing and CQRS pattern
        * Use intelligent caching to improve resilience

* Application delivery patterns
    * Fast feedback via continuous integration
        * Version control is a must
        * Trunk-based development
        * Often coupled with test-driven development
        * CI jobs triggered on code check-in
        * Test in production-like environments
    * Packaging up software
        * Include configuration and code
        * Build service generate artifacts
        * Containers are a useful packaging structure
        * Artifact repositories play a key role
    * Continuously deliver value
        * Small changes, regularly shipped
        * Same binaries in each environment
        * Multiple strategies for low-impact deployments
        * Smoke test and watch metrics to ensure healthy releases

* Application infrastucture patterns
    * Immutable infrastucture
    * Observable systems
    * APIs for interacting with infrastucture
    * Chaos engineering to fight fragility

* Application team patterns
    * Empowered, customer-focused teams
        * DevOps style teams build and run services
        * Platform Ops for managing underlying systems
        * Site reliability engineering applies software engineering approach to operations

## The technologies for Cloud-native architecture

* Application architecture technologies
    * External config including cloud-only services like Azure Key Vault, software like Hashicorp Vault or Spring Cloud Config
    * Code-based microservice infrastucture like Spring Cloud, Steeltoe and Go Micro
    * API gateways from public public cloud providers, or software from Apigee and Microsoft
    * Identity management technologies including oAuth 2.0, OpenID connect and JWT

* Cloud-native database technologies
    * Self-managed, OSS databases like PostGreSQL, MuSQL, MongoDB, and Cassandra
    * Managed cloud databases from Amazon (RDS, DynamoDB), Microsoft (SQL Database, CosmosDB) and Google (Spanner)
    * Self-managed or hosted application caches based on Redis, Memcached and GemFire

* Cloud-native Messaging technologies
    * Brokers like RabbitMQ, ActiveMQ or NATS
    * Event stream processors like Apache Kafka, Apache Flink or WSO2 Stream Processor
    * Cloud-based services like Amazon SQS, Google Pub/Sub, or Azure Event Hubs

* Continuous integration technologies
    * Version control software from GitHub, GitLab, Azure Repos, and Bitbucket
    * Continuous integration workflow tools like Jenkins, Concourse, Circle CI, TeamCity, AXS CodePipeline and Azure Pipelines

* Packaging and Deploying technologies
    * Artifact repositories like JFrog Artifactory, Sonartype Nexus repository, and Apache Archiva
    * Package formats like Linux or Windows containers and package managers like Helm
    * Use CI tools like Concourse or Jenkins, plus software like GoCD and Spinnaker
    * Enable feature flags with services like LaunchDarkly, and analyze post-deploy metrics with DynaTrace and New Relic

* Infrastructure Automation technologies
    * Config management like Chef, Ansible
    * Create infrastucture with Terraform
    * Build and manage systems with BOSH
    * Run containers with Kubernetes, Mesos or Nomad
    * Automate app runtime with PaaS and FaaS
    * Microservices infrastucture with a service mesh

* Collaboration technologies
    * Chat tools like Slack and Microsoft Teams
    * Kanban boards using tools from Trello, Realtime Board, and Asana
    * Shared access to logging and monitoring tools to pinpoint issues
    * Video conferencing tools like Zoom, BlueJeans, Skype, and Google Hangouts