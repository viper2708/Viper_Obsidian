## Principles and concepts

* What is airflow?
    * Airflow is an open source Python framework that allows to programmatically crate, schedule and monitor workflows
    * Principles
        * Scalable
            * Airflow has modular architecture and uses a message queue to orchestrate an arbitrary number of workers. Airflow is ready to scale to infinity
        * Dynamic
            * Airflow pipelines are defined in Python, allowing dynamic pipeline generation. You can easily write code to instantiate workflows dynamically
        * Extensible
            * You can define your own operators and extend libraries to fit the level of abstraction that suits your environment
        * Elegant
            * Airflow pipelines are lean and explicit. Parameterization is built into its core using the powerful Jinja templating engine
    * Features
        * Pure Python
            * Use standard Python features to create your workflows, including date time formats for scheduling and loops to dynamically generate tasks. This allows you to maintain full flexibility when building your workflows
        * Useful UI
            * Monito, schedule and manage your workflows through a robust and modern web application. No need to learn old, cron-like interfaces. You always have full insights into the status and logs of completed and ongoing tasks
        * Robust integrations
            * Airflow provides many plug-and-play operators that are ready to execute you tasks on SG cloud platform. They will help you to easily orchestrate your workflows on hybrid (Legacy and XaaS)
        * Easy to use
            * Anyone with Python knowledge can deploy a workflow. Apache Airflow does not limit the scope of your pipelines. You can use it to build ML models, transfer data, manage your infrastructure and more
        * Open source
            * Wherever you want to share your improvements, you can do so by opening a PR. Airflow has many active users who willingly share their experiences

## Available features and usage

* Cloud orchestration service is broadly based on two layers
    * Control Plane API
        * It manages the life cycle of Airflow instances by providing an interface allowing CRUD operations
    * Resource Plane
        * It allows the clients to deploy their artifacts and manage his workflows using
            * Airflow API - It allows to deploy your artifacts and execute workflows
            * Flower UI - It allows to monitor and administrate Celery clusters
            * Airflow UI - Its allows to manage Airflow instances