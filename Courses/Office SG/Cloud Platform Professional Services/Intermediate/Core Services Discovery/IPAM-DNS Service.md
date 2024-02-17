## Principles and concepts

* IP Address Management (IPAM) is a service for planning and managing the assignment and use of IP addresses and networks. It does not typically provide Domain Name System (DNS) and Dynamic Host Configuration Protocol (DHCP) services, but manages information for these components at SG
* Domain Name System (DNS) is the service for managing SG's domain names. It allows users to translate Cloud Platform resource names into IP addresses (previously reserved in the IPAM). It's the naming system for the Cloud platform resources
* Each IP address used in the DNS is known by the IPAM. In this way, IPAM is the golden source for IP addresses and networks
* The important features of the DNS service are :
    * Define host names in a domain and bind it to an IP address
    * Define aliases for hosts created in domains (also known as FQDNs : Fully Qualified Domain Names)

## Use cases

* Reserve an IP address in a subnet
* Give a human-readable name to my resource in Cloud Platform and associate it with my previously reserved IP
* Create an alias on top of my application front-end in order to be used by my application end users

## Available features and usages

* IPAM/DNS services allow to request an IP, ,manage subnet, manage Hosts or manage DNS aliases
* It's available in a self-service mode(API or web portal)