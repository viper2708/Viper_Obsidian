## Principles and concepts

* What is Block storage for Openstack?
    * Openstack uses 2 types of storages :
        * Ephemeral storage which is meant for Compute installation. Any data on that area will be wiped when a VM is destroyed
        * Persistent storage which is meant for any data that must survive VM deletion or has it's own lifecycle
    * It allows the addition of performace storage to the Virtual Servers created within the Openstack framework
    * Block storage layer brings to Openstack persistent high performance storage class

* Block storage what for?
    * Structured data
    * No data sharing between users or computers
    * Accessibility : Only on Openstack environment (VM) and containers
    * Service offers : Tie-fighter (Medium performance) and X-Win (High performance)
    * Protocol : None - Used to create File System within VMs
    * Optional feature : Snapshots, clone, data mobility

## Available features and usage

* What can i do with Openstack Block storage?
    * Attach a persistent storage to my Openstack VMs
    * Have a low latency storage available for my applications
    * Build and destroy quickly development and testing environments
    * Move my persistent volume from on VM to another
    * Create a copy of my data