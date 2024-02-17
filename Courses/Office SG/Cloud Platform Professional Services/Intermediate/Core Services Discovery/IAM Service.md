
## Principles and concepts

* The IAM service and why you may need it?
    * The founding concepts of the Identity and Access Management(IAM) service can be summarized in 4 key words
        * Permissions
        * Roles
        * Tools to setup permissions and roles
        * Certification rules

* More precisions on the IAM service concepts (1/3)
    * The account model of Cloud Platform is aligned with public cloud principles, billing constraints and security requirements
        * User
            * A user can be a human (developer, application manager, etc.) or technical (called ClientID). Both are considered in the same way by services and the IAM. A user may be granted 1 or several roles by an Account Leader
        * Account
            * In cloud Platform, all resources and roles(permissions) are tied to 1 and only 1 account. An account can represent any project or application, thus 1 account can be used for N users, and 1 user can use N accounts. Resources are tied to 1 and only 1 account. In fact, an account is a billing entity used to gather resources, their permissions and their costs
        * Roles
            * Roles can be seen as a Template of permissions ready to be given to a user. They contain scopes that are keys to use services. A scope allows the user to perform specific operations on the Cloud Platform services, typically CRUD operations on Cloud Platform resources.
        * Account Leader and Security Office
            * An account has 2 main managers : the Account Leader who can grant roles, created by the Security Officer, to Users or Clients in his account. Today, the App Manager has both responsibilities and can create roles and enable any user to the roles tied to the account
        * Provisioning Officer
            * By default, the Provisioning Officer is the manager of a set of users, as described in go/org. The Provisioning Officer (as well as Account Leader) is in charge of validating any request coming from a user is his/her team
        * validation workflows
            * The processes for validating access to SG are a cornerstone of the bank's security and must be replaced.

## Available features and usages

* Today, as an application manager (Account Leader and Security Officer), through WHATS or DIN, i can:
    * Create Roles from a list of predefined scopes (read scopes, write scopes) or by selecting custom scopes
    * Update / Delete Roles
    * List Available Roles
    * Grant / Remove users (and myself)
    * Display scopes attached to a role
    * List members of each role
    * View roles granted to a user
    * Track all ongoing requests pushed by me or by others
    * Validate or refuse user permission requests

* As a developer, through WHATS or DIN, i can:
    * View role description for existing roles
    * Display scopes attached to a role
    * View the roles I have been granted
    * Request permission on an existing role
    * Request permission on a scope not contained in an existing role

* As a Provisioning Officer, through WHATS, i can:
    * Validate or refuse user permission requests