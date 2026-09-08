# API gateways

An `API gateway` is a central entry point that sits between external clients (eg. web apps, mobile apps) and your backend internal services. Instead of clients calling your services directly, they call the API gateway, which then routes requests to the appropriate service.

API gateways are a key design pattern for [microservice architectures](../m/microservice-architectures.md).




This is a single entry point (ingress controller) that sits in from of your microservices and receives requests from external clients and manages:
- authentication
- authorisation
- routing to to the appropriate service from a single exposed endpoint, simplifying client interactions.

API gateways can enforce <mark>rate limiting</mark> on requests from outside:
- controlling the volume of requests a client can make within a given time period
- protecting your backend resources from overload and abuse
- supporting strategies like quotas, throttling, burst control
- improving system stability during traffic spikes.



----

Back up to: [Maglocvnus](../index.md)
