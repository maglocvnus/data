# Performance tuning

Database `performance tuning` involves tweaking the design of a database to make query response times shorter (ie. decreasing latency). 
This is one of the most important tasks carried out by a traditional database administrator.

There are three main techniques for performance tuning a relational database:
- [indexing](../i/indices.md) a table on a frequently accessed column (or set of columns)
- [clustering](../c/clusters.md) tables which are frequently joined in queries, by ensuring related rows are physically stored together on disk
- [partitioning](partitions.md) a large table into smaller tables, by row (horizontal partitioning), or by column (vertical partitioning).

----

Back up to: [Maglocvnus](../index.md)
