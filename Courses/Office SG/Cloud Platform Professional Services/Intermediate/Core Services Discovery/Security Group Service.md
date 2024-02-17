# Security Group Service

## Principles and concepts

*  What is micro segmentation?
    * Micro segmentation is a security solution that enables fine-grained network filtering policies to be assigned to datacenter applications down to the workload level. With micro segmentation, security settings can be tailored to different types of traffic, creating policies that limit network and application flows between workloads to those that are explicitly permitted. The goal is to decrease the network attach surface. By applying the segmentation rules down to the micro level of the workload or application, the risk of an attacker moving from one compromised workload or app to another is reduced
    * Micro segmentation is the best way to prevent the spread if threats inside your data centres and Cloud environment

* What is security group?
    * A security group is a set of firewall rules for your instance to control incoming and outgoing traffic
        * Inbound rules control the incoming traffic to your VM instance, and outbound rules control the outgoing traffic from your VM instance
        * When you launch an instance, you can specify one or more security groups; otherwise, the default security group is applied
        * You can modify the rules for a security group at any time. New and modified rules are automatically applied to all instances that are associated with the security group
        * Unlike network access control lists (NACLs), there are no 'Deny' rules. If there is no rule that explicitly permits a particular data packet, it will be dropped
        * Only allow the access that is needed for your application or service, and do not apply overly permissive access as this can result in future security breaches and vulnerabilities

## Available features and usages

* Features available today
    * Manage security group for an Account :
        * Create a security group
        * Fetch a security group
        * Update a security group
        * Delete security group
    * Manage firewall rules of security group of an Account
        * Create firewall rule in a security group
        * Fetch a firewall rule
        * Delete firewall rules
    * Attach or Detach a Security Group to an OCS VM
    * Debug flows for a given Account