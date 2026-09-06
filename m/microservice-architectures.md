# Microservice architectures

Distributed architectures ? same thing?

components/containers up to systems??

Opposite = monolithic architecture / monolith 

application 

Microservices = applications with loosely coupled components that communicate with each other across a network (ie. TCP/IP?).

A small independent component that implements a single self contained atomic business capability.

Trad monolith = one code-base, one deployment unit, to update one capability you need to redeploy the entire application

Each microservice is owned by an independent team, can be deployed, scaled, updated without impacting other services.

Microservices communicate over APIS, and each has its own database.


Microservices are not containers, though containers are often used to package micro services. Microservices are about **business capability separation**.

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
