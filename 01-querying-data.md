# Querying Data From Tables

## Querying data from one or more tables

Query data in columns c1, c2 from a table
```sql
SELECT c1, c2 FROM t;
```

Query all rows and columns from a table
```sql
SELECT * FROM t;
```

Query data and filter rows with a condition
```sql
SELECT c1, c2 FROM t
WHERE condition;
```

Query distinct rows from a table
```sql
SELECT DISTINCT c1 FROM t
WHERE condition;
```

Sort the result set in ascending or descending order
```sql
SELECT c1, c2 FROM t
ORDER BY c1 ASC [DESC];
```
Skip offset of rows and return the next n rows
```sql
SELECT c1, c2 FROM t
ORDER BY c1 
LIMIT n OFFSET offset;
```
Group rows using an aggregate function
```sql
SELECT c1, aggregate(c2)
FROM t
GROUP BY c1;
```

Filter groups using HAVING clause
```sql
SELECT c1, aggregate(c2)
FROM t
GROUP BY c1
HAVING condition;
```

Inner join t1 and t2
```sql
SELECT c1, c2 
FROM t1
INNER JOIN t2 ON condition;
```

Left join t1 and t1
```sql
SELECT c1, c2 
FROM t1
LEFT JOIN t2 ON condition;
```

Right join t1 and t2
```sql
SELECT c1, c2 
FROM t1
RIGHT JOIN t2 ON condition;
```

Perform full outer join
```sql
SELECT c1, c2 
FROM t1
FULL OUTER JOIN t2 ON condition;
```

Produce a Cartesian product of rows in tables
```sql
SELECT c1, c2 
FROM t1
CROSS JOIN t2;
```

Another way to perform cross join
```sql
SELECT c1, c2 
FROM t1, t2;
```

Join t1 to itself using INNER JOIN clause
```sql
SELECT c1, c2
FROM t1 A
INNER JOIN t2 B ON condition;
```

## SQL Operators

Combine rows from two queries
```sql
SELECT c1, c2 FROM t1
UNION [ALL]
SELECT c1, c2 FROM t2;
```

Return the intersection of two queries
```sql
SELECT c1, c2 FROM t1
INTERSECT
SELECT c1, c2 FROM t2;
```

Subtract a result set from another result set
```sql
SELECT c1, c2 FROM t1
MINUS
SELECT c1, c2 FROM t2;
```

Query rows using pattern matching %, _
```sql
SELECT c1, c2 FROM t1
WHERE c1 [NOT] LIKE pattern;
```

Query rows in a list
```sql
SELECT c1, c2 FROM t
WHERE c1 [NOT] IN value_list;
```

Query rows between two values
```sql
SELECT c1, c2 FROM t
WHERE  c1 BETWEEN low AND high;
```

Check if values in a table is NULL or not
```sql
SELECT c1, c2 FROM t
WHERE  c1 IS [NOT] NULL;
```
