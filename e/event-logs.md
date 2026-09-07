# Event logs

An `event log` is an ordered, persistent history of all the events that have happened in a data system.

An event log is generally append-only and hence immutable – corrections are handled by appending a new event.

Events in an event log are typically time-stamped.

An event log provides a complete audit trail of changes in a data system.

An event log is used in the architectural design pattern [event sourcing](event-sourcing.md), as the source of truth from which current state is derived.

----

Back up to: [Maglocvnus](../index.md)
