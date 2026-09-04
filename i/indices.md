# Indices

A relational database `index` is an auxiliary table which: 
- is derived from some base table in the database, by selecting one or more frequently queried columns
- is kept sorted on that column
- gives the location of the relevant row in the base table.

Indexing a table is the most common technique for [performance tuning](../p/performance-tuning.md) a database (ie. shortening query response times).

## The problem

Take the following base table:

| given name | surname | age |
| - | - | - |
| Kate | Runson | 33 |
| Jason | Dorr | 51 |
| Alexa | Verre | 25 |
| Andy | Whyte | 59 |
| Emma | Borat | 53 |
| Gill | Turnbull | 49 |
| Carolina | Garcia | 32 |
| Pauline | Marshall | 63 |
| Pedro | Silva | 37 |
| Mike | Small | 58 |

Imagine that the most common query type on this table is to retrieve a person’s age from their surname, as in:

```
SELECT age FROM table WHERE surname='Garcia'
```

Assuming this table has *N* rows, the number of row lookups a standard sequential search will take to find a surname will be:
- *N*/2 in the average case
- *N* in the worst case.

If the table has millions of rows, this will significant impact query response times, and lead to a diminished user experience. 

## The solution

One obvious solution might seem to keep the base table **sorted** by surname, since we know that searching a sorted list is much faster than searching an unsorted one.

However, this would make inserting new records (and updating existing surnames) much slower.

The most common solution is to *index* the table on the `surname` column.

This involves getting the relational database management system to create a new <mark>index</mark> table, like this one here:

| surname | row |
| - | - |
| Borat | 5 |
| Dorr | 2 |
| Garcia | 7 |
| Marshall | 8 |
| Runson | 1 |
| Silva | 9 |
| Small | 10 |
| Turnbull | 6 |
| Verre | 3 |
| Whyte | 4 |

This index has the same number of rows as the base table, but only has two columns:
- the surname column, kept in alphabetical order
- the row number of the record in the base table.

When the database system is processing a query like the following:

```
SELECT age FROM table WHERE surname='Garcia'
```

It will first of all look up `Garcia` in the surname index and retrieve the base table row number.

HERE


When the database system is running a query involving a condition like name = ‘Kate’, the query optimiser will first of all look up ‘Kate’ in the sorted name index (should it exist) to find the location (row number) of the relevant record in the base table. It will then use that row number to directly access the record in the base table, without having to access any other records.

The primary key column for a table is automatically indexed. When inserting a new row in a table, the database system will first of all check this index to make sure that a row with the same primary key value does not already exist.

You should create indexes for your table carefully:
- Indexes take up disk space (not so much of an issue nowadays).
- Indexes need to be updated for every write operation on the base tables, slowing these down considerably.

You should create additional indexes for columns which are referred to frequently in queries.

You should avoid creating indexes on clumns that contain non-discriminatory data ie. only a handful of values throughout the entire table (eg. binary data like booleans, etc.)


mmm

----

Back up to: [Maglocvnus](../index.md)
