# Microservice architectures

A `microservice` architecture is a distributed system consisting of small, loosely coupled software applications, each of which typically:
- implements a single, self-contained, atomic business capability
- is developed and owned by its own independent software team
- has its own code base (repository)
- is independently deployable, scalable and updatable
- communicates with other applications over a (TCP/IP) network, via a well-defined interface.

In terms of data architecture, each microservice typically has: 
- its own decentralised *data layer*
- which includes its own database (eg. SQL, NoSQL, graph databases, data lakes).

Communication between microservices can be:
- request-driven (synchronous) eg. via REST APIs
- event-driven (asynchronous) eg. via message or event brokers.

Microservice architectures contrast with traditional *monolithic* applications, where all functionality is bundled into one code base and one deployment unit. Communication within a monolith is generally via direct method/function calls, since all components share the same memory space. In a monolith, scaling is difficult, and changes are risky.

The historical evolution of distributed software has had three stages: 
- 1990s – *Remote Procedure Call* (RPC), where one application can execute a function on another computer over a network as if it were calling a local function (eg. `Customer.getCustomer(23)`), and RPC handles the network communication behind the scenes
- 2000s – *Service Oriented Architectures*, with domain-specific services, centrally governed via an *Enterprise Service Bus* (ESB) for routing, transformation, protocol conversion, orchestration.
- 2010s – (decentralised) microservices.

security is more complex because you need to protect multiple service to service communications instead of a single application perimeter; need to implement authentication and authorisation using patterns like Auth2 and JWT tokens; you need to secure all communication channels with TLS encryption.


The main benefits of microservice architectures over traditional monolithic architectures are:
- faster release cycles – you can redeploy one service without full application redeployment (agility)
- independent scaling – you can grow hot paths with over-provisioning everything
- fault/failure isolation – a single service failing does not stop your entire system (resilience).

The main challenges for microservice architectures are:
- You have to manage the complexity of distributed systems, and need to invest in orchestration platforms (eg. Kubernetes)
- There is a huge backlog of network connections to protect (exponential perimeter surface growth)
- services can be ephemeral so you need robust dynamic service discovery mechanism
- you need sophisticated observability with centralised logging, metrics, and distributed tracing






For data architecture specifically:
- Microservices can eliminate the shared database bottleneck of traditional monoliths.
- But challenges arise concerning data consistency, and transactions across services.







To operate microservices effectively, you typically need a service mesh – dedicated infrastructure providing authentication, authorisation, routing and load balancing, security monitoring.

So you need an API gateway to route requests and service discovery mechanisms for dynamic service lookups.

Microservice security is more complex (3.30)




----

Back up to: [Maglocvnus](../index.md)
