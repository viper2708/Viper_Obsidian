## Principles and concepts

* What is a virtual server
    * A virtual server is a compute instance from images, sized by a flavor, communicating via a network, and secured by authentication mechanism
        * Virtual server : The compute instance itself
        * Network : The network zone of the instance
        * Flavor : Amount of CPU / Disk / RAM of the instance
        * Images : Template of the Operating system
        * Authentication mechanism : Public part of the SSH keypair used to log into the instance
    * For the creation of a virtual server, we have 2 platforms
        * OCS : Openstack Compute Services (Cloud Native No Ops)
        * VCS : VMware Compute Services (Cloud Lift and Shift)

## Available features and usages

* What are the mode of consumption of Cloud Platform?
    * Virtual server service is to submit from the Cloud Platform or API. It's available in self-service : no more need to contact the GTS team
        * Virtual server can be consumed in 2 ways
            * Programmatically / via API
                * Enable to automate Virtual server creatives
            * Graphically / via a web portal
                * From DoItNow, it is possible to build and manage these Virtual servers

* What are the main features of the Virtual server service?
    * Create, list and destroy Virtual Server instances
    * Create, list and destroy Server Groups
    * Add, list, change and delete tags on Virtual Server instances
    * Add, list, change and delete metadata on Virtual Server instances
    * List available subnets for Virtual Server instances
    * Reboot or start a stopped Virtual Server instance
    * Get the console output of my Virtual Server instance
    * Resize my Virtual Server instance