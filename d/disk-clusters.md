# Disk clusters

A `disk cluster` is a relational database artifact that ensures that related rows from two or more frequently joined tables are physically stored near each other on disk.

Disk clustering is a common technique for [performance tuning](../p/performance-tuning.md) a database (ie. shortening query response times).

### The problem


### The solution


You can speed up certain complex queries involving joins by creating disk clusters, which try to reduce the number of times the DBMS has to read from disk, so as to speed up performance.

Note that a DBMS retrieves data from disk one whole ‘disk page’ at a time.

A cluster is defined by a DBA to ensure that data that is often accessed together is kept together on disk as closely as possible (on the same page or on adjacent pages). This means rows that are related to each other through primary and foreign keys, even though they may belong to different tables.

A table can be clustered on only one column (or combination of columns).

Clustering can slow down queries that require scanning a whole logical table (since the rows in that table are scattered across different pages on disk).

Clustering can slow down write operations (both insertions and updates).


----

Back up to: [Maglocvnus](../index.md)
