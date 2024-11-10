# Object Storage Service

## Principles and concepts

* What is object storage?
    * Object Storage is a way to store data without depending on a file system structure which makes it genuinely cross platform
    * As well as objects, related description of that object, referred as metadata, are stored. This makes large type of data easy to handle across various systems
    * Using AWS S3 (Simple Storage Service) - now a defacto standard - data are widely accessible using simple HTTPS queries using IAM for authentication
    * Objects are stored within containers referred as buckets

## Use cases

* What are the best use cases of Object Storage?
    * Unstructured data such as media and application files (like archive files, picture)
    * Data sharing between users and computers

* Main characteristics of the offer
    * Accessibility : Everywhere
    * Service offers : Toad (no multi AZ resiliency) and Yoshi (multi resiliency on same region)
    * Access protocol : S3 (through HTTPS)
    * Optional features : Versioning, life cycle, data mobility (replication)

## Available features and usages

* Standard and low flavors are differentiated by data protection level (mono or dual AZ)
* Object Storage offer is available in several regions
* No limitations on the number of objects within a bucket