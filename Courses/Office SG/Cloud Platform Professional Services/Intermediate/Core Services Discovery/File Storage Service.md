## Principles and concepts

* What is file storage?
    * File storage is a Cloud Platform service which provides storage over network (NAS)
        * It allows applications to share data between multiple Vms (OCS/VCS)
        * It is designed to meet business requirements (costs optimized, high performance, high availability within region or cross regions)
        * It is API driven (create, delete, size, etc.)
        * It also comprises of advanced features such as user triggered snapshots, consistency group, encryption and more
    * File storage manages both structured and unstructured data and is an ideal solution for workloads that rely on shared file systems for use cases like
        * Transactional applications
        * Database live applications
        * Database dumps
        * Business connectivity
        * Disaster recovery
        * Containers
        * Big data

* What does file storage have?
    * Data sharing between users or computers with high performance and low latency
    * Accessibility : Everywhere (on internal SG network - Not available on DMZ / Web / Cloud cells)
    * Suitable for both Structured and Unstructured data
    * Protocol : NFSv4 and above
    * Service offers : Premium offer without Replication, Premium offer with Mono-region Replication, Premium offer with Cross-region Replication 
    * Optional features : Replication, Snapshots, Clone, Failover, Grow, etc.

## Available features and usage

* Features available today
    * Create a Mono-AZ resilient file system that can be shared across multiple VM's using NFSv4 Protocol
    * Create a consistency group for logical grouping of file systems
    * List and delete File systems
    * List and delete consistency groups
    * Grant and revoke access on file system to compute hosts
    * Create / List / Delete a Snapshot of consistency group