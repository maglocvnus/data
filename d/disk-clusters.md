# Disk clusters

A `disk cluster` is a relational database artifact that ensures that related rows from two or more frequently joined tables are physically stored near each other on disk.

Disk clustering is a common technique for [performance tuning](../p/performance-tuning.md) a database (ie. shortening query response times).

### The problem

Take the following base table, storing records about people and their names:

| id | given name | surname |
| - | - | - |
| 1 | Kate | Runson |
| 2 | Jason | Dorr |
| 3 | Alexa | Verre |
| 4 | Andy | Whyte |
| 5 | Emma | Borat |
| ... | ... | ... |

And another table which is related to the previous table using a foreign key, giving age information about each person:

| person | age |
| - | - |
| 1 | 33 |
| 2 | 51 |
| 3 | 25 |
| 4 | 59 |
| 5 | 53 |
| ... | ... |

Let’s assume that each table is stored on a different disk page.

Let’s also assume that the most common user queries involve joining related rows from these two table:

```
SELECT ages.age
FROM people JOIN ages ON ages.person = people.id
WHERE people.surname = 'Runson'
```

To process this query, the database management system will need to:
1. Locate and read in the disk page containing the first rows of the `people` table.
2. Locate and read in the disk page containing the relevant row of the `ages` table.

Since reading in disk pages is a relatively time-consuming process, this can slow things down considerably.

### The solution

To speed things up, you can ask the relational database management system to create a dedicated <mark>disk cluster</mark>, which will ensure that related rows from different tables are stored together on the same disk page (or perhaps on adjacent pages). 

This means that each query will require just one read from disk, and hence will speed up query responses significantly.

### Notes

Some overheads of disk clustering:
- It may slow down queries that require scanning a whole logical table, since the rows in that table are scattered across different pages on disk.
- It may slow down write operations – both insertions and updates.

Disk clustering is a built-in feature of certain large database systems, such as Oracle.

----

Sources: 
- Jon L. Harrington (2016). *Relational Database Design and Implementation*, 4th Edition. O’Reilly. Chapter 8: ‘Database design and performance tuning’.

----

Back up to: [Maglocvnus](../index.md)
