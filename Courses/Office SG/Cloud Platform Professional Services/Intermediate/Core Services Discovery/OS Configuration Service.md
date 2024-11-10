## Principles and concepts

* What is OS configuration?
    * OS configuration (or OSC) is the service that allows you to modify your server configuration with Puppet recipes (also called modules) available in a maintained catalogue.
    * The context :
        * Business applications require to deploy and configure components on new servers when they are not already installed in the base image from which those servers are instantiated
    * The standard :
        * Some configurations are mandatory within SG. Typically :
            * The configuration of the security components included on the base image provided by GTS is always enforced by OSC
            * The hardening of the servers is also enforced by OSC
            * Finally, you cannot modify configurations under the control if OSC
    * The service :
        * The OSC service allows you to modify server configuration based on catalog if recipes
        * You can also create your own recipes, validated by a CI/CD pipeline, and use them through OSC

## Available features and usages

* What are the features of the OS configuration service?
    * List of all available modules in catalog
    * Associate modules to a server
    * Execute a run of puppet agent
    * Get status of the run of the agent
    * Create new module in the OSC catalog
    * Change server from production environment to OSC development one