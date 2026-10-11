# Data quality








## Audit trails

Many data quality issues result from user error. 

In order to diagnose such issues, a data architect can design an <mark>audit trail</mark> into the database, so that it can keep track of who has entered data.
- One simple audit trail technique is to include a column in every table for the user ID of the person who inserted (or ‘entered’) the row of data.
- Alternatively, every row in a table can have its own row ID column, distinct from the primary key and row number. This table can be accompanied by a separate ‘audit table’ where each row records a modification made to the original table, using the row ID as a foreign key, and specifying who did what to that row at what time on what date. 

Some database management systems have audit trail capabilities built-in, for example Oracle.

----

Back up to: [Maglocvnus](../index.md)
