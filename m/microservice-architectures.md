# Microservice architectures

A `microservice` architecture is a distributed system consisting of small, loosely coupled software applications, each of which typically:
- implements a single, self-contained, atomic business capability
- is developed and owned by its own independent software team
- has its own code base (repository)
- is independently deployable, scalable and updatable
- communicates with other applications over a (TCP/IP) network, via a well-defined interface, with traffic encrypted using Transport Layer Security (TLS) encryption
- uses patterns like Auth2 and JWT tokens for authentication and authorisation.

In terms of data architecture, each microservice typically has: 
- its own decentralised *data layer*
- which includes its own database (eg. SQL, NoSQL, graph databases, data lakes).

Communication between microservices can be:
- request-driven (synchronous) eg. via REST APIs
- event-driven (asynchronous) eg. via message or event brokers.

Security is complex in a microservice architecture, since you need to protect multiple service-to-service communications, instead of just a single application perimeter.

Microservice architectures contrast with traditional *monolithic* applications, where all functionality is bundled into one code base and one deployment unit. Communication within a monolith is generally via direct method/function calls, since all components share the same memory space. In a monolith, scaling is difficult, and changes are risky.

The historical evolution of distributed software has had three stages: 
- 1990s – *Remote Procedure Call* (RPC), where one application can execute a function on another computer over a network as if it were calling a local function (eg. `Customer.getCustomer(23)`), and RPC handles the network communication behind the scenes
- 2000s – *Service Oriented Architectures*, with domain-specific services, centrally governed via an *Enterprise Service Bus* (ESB) for routing, transformation, protocol conversion, orchestration.
- 2010s – (decentralised) microservices.

### Benefits and challenges

The main **benefits** of microservice architectures over traditional monolithic architectures are:
- *faster release cycles* – you can redeploy one service without full application redeployment (agility)
- *independent scaling* – you can grow ‘hot paths’ without over-provisioning everything
- *fault isolation* – a single service failing does not stop your entire system (resilience).

The main **challenges** for microservice architectures are:
- You have to manage the complexity of distributed systems, by investing in orchestration platforms (eg. Kubernetes).
- There is a huge backlog of network connections to protect (exponential perimeter surface growth).
- Services can be ephemeral, so you need a robust dynamic *service discovery mechanism* (allowing microservices to find and communicate with each other without hard-coding IP addresses or hostnames).
- You need sophisticated observability with centralised logging, metrics, and distributed tracing.

For data architecture specifically:
- Microservices can eliminate the *shared database bottleneck* of traditional monoliths.
- But challenges arise concerning *data consistency*, and *transactions* across services.

### API gateways and service meshes

You can manage **external** connections between your microservice architecture and clients using an <mark>API gateway</mark> as a front-door.

This is a single entry point that sits in from of your microservices and receives requests from external clients and manages:
- authentication
- authorisation
- rate limiting
- routing to to the appropriate service from a single exposed endpoint.

You can manage **internal** communications among your microservices using a <mark>service mesh</mark>.

This is a dedicated infrastructure layer to handle:
- authentication
- authorisation
- service discovery
- routing
- load balancing
- TLS encryption
- monitoring and observability.


Microservices architecture patterns:
- API gateway pattern
- database-per-service pattern - polyglot persistence
- rate-limiting pattern
- strangler fig pattern
- circuit breaker pattern
- event sourcing and CQRS
- 



----

Back up to: [Maglocvnus](../index.md)
