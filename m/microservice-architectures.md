# Microservice architectures

A `microservice` architecture is a distributed system consisting of small, loosely coupled software applications, each of which typically:
- implements a single, self-contained, atomic business capability
- is developed and owned by its own independent software team
- has its own code base (repository)
- is independently deployable, scalable and updatable
- communicates with other applications over a (TCP/IP) network, via a well-defined interface.

In terms of data architecture, each microservice typically has: 
- its own decentralised *data layer*
- including its own database (eg. SQL, NoSQL, Graph-based, Data Lake).

Communication between microservices can be:
- request-driven (synchronous) eg. via a REST API
- event-driven (asynchronous) eg. via a message or event broker.

Monolithic here?


The main benefits of microservice architectures over traditional monolithic architectures are:
- faster release cycles
- independent scaling
- fault/failure isolation

The main challenges of microservice architectures are:
- You have to manage the complexity of distributed systems, and need t invest in orchestration platforms (eg. Kubernetes)
- There is a huge backlog of network connections to protect (exponential perimeter surface growth)
- services can be ephemeral so you need dynamic service discovery mechanism
- you need sophisticated observability with centralised logging, metrics, and distributed tracing

- decentralised governance


Data architecture:
- benefits: eliminates database bottlenecks 
- challenges: data consistency, transactions across services (data arch)

The opposite of a microservice architecture is usually known as a *monolith* – a traditional multi-component software application characterised by a single code base, deployment unit, database, update windows etc.
- all functionality is bundles into one code base one deployment unit
- communication between components via direct method/function calls (all component share sam memory space)


sailing is difficult, changes are risky, 


diagram of microservices each containing an interface and a database

The historical evolution of distributed software has three stages: 
- 1990s – distributed applications (Network RPC)
- 2000s – Service Oriented Architectures (ESB Enterprise Service Bus, involving central control)
- 2000s – microservices (decentralised government)

To operate microservices effectively, you typically need a service mesh – dedicated infrastructure providing authentication, authorisation, routing and load balancing, security monitoring.

So you need an API gateway to route requests and service discovery mechanisms for dynamic service lookups.


Microservice security is more complex (3.30)

request driven versus event driven communication (synchronous vs. asynchronous)



----

Back up to: [Maglocvnus](../index.md)
