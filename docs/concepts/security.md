# Security

* Securing Connected Data
* Application Level Security
* Authentication
    * LDAP
    * Two Factor
* Authorization
    * RBAC
    * Subgraph
    * Vertex
    * Attribute
* Logging
* Audits

## Securing Connected Data
Why scale and secure first designs are more sustainable.

## Application Level Security

## Authentication

## Authorization

### Role-based Access Control
An design pattern for restricting system access to authorized users based on the roles they have been assigned.

RBAC systems are highly scalable and preferred by most large enterprises.  RBAC systems are scalable because creating individual relationships between a user an an application is too complex and difficult to maintain.

The following are the levels of RBAC within an EKG:

* Subgraph level RBAC - where roles restrict access permission (read, write etc.) to a subgraph
* Vertex level RBAC - where roles restrict access permission (read, write etc.) to each vertex of a graph
* Attribute level RBAC - where roles restrict access permission (read, write etc.) to specific attributes of a vertex or a property
* Query level RBAC - where only specific roles can execute a query

Enterprise scale graphs support vertex-level data access rules.  Although there are performance concerns implementing RBAC, most enterprise systems require this fine grain control.

![NIST RBAC](img/role-based-access-control.jpg)

* [Wikipedia Page on RBAC](https://en.wikipedia.org/wiki/Role-based_access_control)
* [Wikipedia Page on NIST RBAC](https://en.wikipedia.org/wiki/NIST_RBAC_model)