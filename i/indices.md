# Indices

A database `index` is an auxiliary table derived from some base table in the database which: 
- is kept sorted on some frequently queried column (or set of columns) in the base table, and
- gives the location of that row in the base table.

Indexing a table on a frequently accessed column (or set of columns) is the most commonly used techniques for [performance tuning](../p/performance-tuning.md) a database (ie. shortening query response times).




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
