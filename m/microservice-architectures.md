# Microservice architectures

A `microservice architecture` is a distributed system consisting of small, loosely coupled software applications, each of which typically:
- implements a single, self-contained, atomic business capability
- is developed and owned by its own independent software team
- has its own code base (repository)
- is independently deployable, scalable and updatable
- communicates with other applications over a (TCP/IP) network, via a well-defined interface (ie. synchronous REST API, asynchronous messaging or events)
- has its own database (data layer), eliminating database bottlenecks, and potentially introducing polyglot persistence.

The opposite of a microservice architecture is usually known as a *monolith* – a traditional multi-component software application characterised by a single code base, deployment unit, database, update schedule etc.


diagram of microservices each containing an interface and a database

The historical evolution of distributed software has three stages: 
- 1990s – distributed applications (Network RPC)
- 2000s – Service Oriented Architectures (ESB Enterprise Service Bus, involving central control)
- 2000s – microservices (decentralised government)

To operate microservices effectively, you need a service mesh – dedicated infrastructure providing authentication, authorisation, routing and load balancing, security monitoring.

So you need an API gateway to route requests and service discovery mechanisms for dynamic service lookups.


Microservice security is more complex (3.30)




----

Back up to: [Maglocvnus](../index.md)
