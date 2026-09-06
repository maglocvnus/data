# Microservice architectures

A `microservice architecture` is a distributed software system consisting of small, loosely coupled applications, each of which typically:
- implements a single, self-contained, atomic business capability
- is developed and owned by an independent team
- has its own code base (repository)
- is independently deployable, scalable and updatable
- communicates with other applications over a (TCP/IP) network, via a well-defined interface (eg. API, messaging, events)
- has its own database.


The opposite of a microservice architecture is known as a monolithic architecture.
- single code base
- one deployment unit
- one database
- to update one capability you need to update the entire application


diagram of microservices each containing an interface and a database






Historical evolution:
- Distributed applications (1990s) – Network RPC
- SOA (service oriented architectures, 2000s) – ESB Enterprise Service Bus – central control
- Microservices (2010s) – decentralised government

To operate microservices effectively, you need a service mesh – dedicated infrastructure providing authentication, authorisation, routing and load balancing, security monitoring.

Microservices use synchronous communication like REST for immediate responses.

As well as asynchronous messages for events and longer running processes.

So you need an API gateway to route requests and service discovery mechanisms for dynamic service lookups.

Microservices use decentralised data layers
- each service has its own database
- eliminates the database bottleneck
- introduces challenges around data consistency and transactions across services
- may be implemented using different database systems - SQL, graph databases, data lakes

Microservice security is more complex (3.30)




----

Back up to: [Maglocvnus](../index.md)
