# Event sourcing

`Event sourcing` is a data architectural design pattern, where [events logs](event-logs.md) are used as the source of truth from which current state is derived.

Event sourcing is often used alongside [Command Query Responsibility Segregation](../c/CQRS.md) (CQRS):
- The event log is the authoritative write model.
- Conventional, denormalised databases are derived from the event log, and used as convenient, highly scalable read models.

----

Back up to: [Maglocvnus](../index.md)
