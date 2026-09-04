# Indices

A database `index` is an auxiliary table which: 
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

Sorting the base table?

Searching a sorted list is much more efficient than sequential search.


Index on surnames

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



mmm

----

Back up to: [Maglocvnus](../index.md)
