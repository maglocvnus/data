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
- which includes its own dedicated database – known as the *database-per-service* design pattern.
- You can choose the optimal database technology for each service’s specific needs – SQL, NoSQL, graph databases, data lakes – known as <mark>polyglot persistence</mark>.
- Services can evolve data models independently.
- However, this requires sophisticated distributed consistency strategies like *sagas* and *event-driven architectures*.

Communication between microservices can be:
- request-driven (synchronous) eg. via REST APIs
- event-driven (asynchronous) eg. via message or event brokers.

Security is complex in a microservice architecture, since you need to protect multiple service-to-service communications, instead of just a single application perimeter.

### From monoliths to microservices

Microservice architectures contrast with traditional *monolithic* applications, where all functionality is bundled into one code base and one deployment unit. Communication within a monolith is generally via direct method/function calls, since all components share the same memory space. In a monolith, scaling is difficult, and changes are risky.

The historical evolution of distributed software has had three stages: 
- 1990s – *Remote Procedure Call* (RPC), where one application can execute a function on another computer over a network as if it were calling a local function (eg. `Customer.getCustomer(23)`), and RPC handles the network communication behind the scenes
- 2000s – *Service Oriented Architectures*, with domain-specific services, centrally governed via an *Enterprise Service Bus* (ESB) for routing, transformation, protocol conversion, orchestration.
- 2010s – (decentralised) microservices.

### Benefits and challenges of microservice architectures

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

### Other factors

You can manage **external** connections between your microservice architecture and clients using an [API gateway](../a/API-gateways.md) as a front-door. API gateways are a key design pattern for microservice architectures, shielding your internal APIs, and offloading common functionality from individual services – routing, authentication, encryption, rate limiting, monitoring etc.

You can manage **internal** communications among your microservices using a [service mesh](../s/service-meshes.md). Services meshes provide common services like routing, authentication, authorisation, service discovery, load balancing, mTLS encryption, etc.

The [strangler fig](../s/strangler-fig.md) strategy provides a safe incremental approach to migrating from a monolithic architecture to microservices:
- gradually replacing monolithic functionality by routing specific endpoints to new microservices, while keeping the monolith operational
- using the API gateway to intelligently routing requests based on defined rules
- allowing for phased migration with minimal risk
- providing easy rollback capability if issues arise.

### Circuit breaker pattern

The <mark>circuit breaker</mark> pattern prevents cascaded, system-wide failures in distributed systems:
- failure rates and response times of downstream services are constantly monitored
- when a threshold is exceeded, the circuit is opened so as to stop forwarding requests to the failing service
- this enables graceful degradation with fallback strategies, eg. cached responses, default values.

The circuit breaker has three states:
- closed – normal operation
- open – failure protection
- half-open – testing recovery.

### Event sourcing and CQRS

Microservice architectures often combine two other architectural design patterns:
- [event sourcing](../e/event-sourcing.md) – [event logs](../e/event-logs.md) are used as the source of truth from which current state is derived
- [command query responsibility segregation](../c/CQRS.md) (CQRS) – use different, independently optimised data models for writes and reads in the same system.

Thus, the event log can serve as the authoritative write model, with derived, conventional, denormalised databases as convenient, highly scalable read models.

----

Back up to: [Maglocvnus](../index.md)
