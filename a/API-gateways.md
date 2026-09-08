# API gateways

An `API gateway` is a central entry point that sits between external clients (eg. web apps, mobile apps) and your backend internal services. Instead of clients calling your services directly, they call the API gateway, which then routes requests to the appropriate service.

API gateways are a key design pattern for [microservice architectures](../m/microservice-architectures.md).

API gateways provide the following front-door (or ‘reception’) services: 
- request routing – routes requests to the correct backend service, so that clients only need to know about the gateway
- authentication and authorisation – verifying identity before forwarding requests, meaning that an individual internal service doesn’t have to validate tokens itself
- SSL/TLS termination – handling HTTPS encryption and centralising certificate management
- rate limiting and throttling – protecting services from excessive traffic
- load balancing – distributing traffic across multiple instances, improving scalability and reliability
- request and response transformation – modifying requests or responses eg. adding headers, removing sensitive fields, converting formats, aggregating results from multiple services
- monitoring and logging – collecting request logs, response times, error rates, usage metrics 

----

Back up to: [Maglocvnus](../index.md)
