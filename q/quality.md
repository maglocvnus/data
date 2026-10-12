# Data quality

`Data quality` is a measure of how accurate and up-to-date your business data is.

Data quality is important because the reliability of any strategic or operational business decisions is directly proportionate to the quality of the underpinning data – garbage in, garbage out! Bad data leads to the business suffering – lost sales, customer dissatisfaction, etc.

It is much easier to assure data quality **before** it gets into the database.

## Missing data

One important measure of data quality is `completeness` – the proportion of the data that **should** be there that actually are there.

Data can be missing for two main reasons:
- Data should have been entered into the database but wasn’t.
- Data *was* entered into the database but was subsequently wrongly deleted.

### Missing rows

One important sub measure of data completeness is `record completeness` – the proportion of the records (rows, entities) that should be there and actually are.

One common reason for records being missing is that some user has been using low-level data manipulation tools and has accidentally either deleted rows, or missed rows out when copying data between tables. It should be noted here that using low-level tools to manipulate rows in a database violates one of Codd’s rules – it should not be possible for users to circumvent data integrity rules using low-level tools.

Missing records can be very hard to detect, if their absence doesn’t violate any referential integrity constraints.

Similarly, it can take a lot of time and effort to locate the source of the problem, and in certain cases it may be impossible – packets lost in transit across the internet, customer error, etc.

Another source of missing records is where a user tries to insert a new record with an incomplete primary key (eg. one column is missing), and the database rejects the new row. The solution to this kind of problem is to design your tables to have arbitrary primary keys. 

### Missing column values

Another important sub-measure of data completeness is `relation completeness` – the proportion of the relations (cell values) that should be there (ie. non-`NULL`) and actually are.

Note that `NULL` values that are not explicitly `REQUIRED` do not impact on data quality – unlike column values that are required but missing.

The problem of detecting and fixing relation incompleteness can be straightforwardly solved by implementing data integrity controls that explicitly disallow `NULL` values in particular columns.




## Audit trails

Many data quality issues result from user error. 

In order to diagnose such issues, a data architect can design an <mark>audit trail</mark> into the database, so that it can keep track of who has entered data.
- One simple audit trail technique is to include a column in every table for the user ID of the person who inserted (or ‘entered’) the row of data.
- Alternatively, every row in a table can have its own row ID column, distinct from the primary key and row number. This table can be accompanied by a separate ‘audit table’ where each row records a modification made to the original table, using the row ID as a foreign key, and specifying who did what to that row at what time on what date. 

Some database management systems have audit trail capabilities built-in, for example Oracle.

----

Back up to: [Maglocvnus](../index.md)
