# Querying data from one or more tables

General syntax
```sql
SELECT TargetList
FROM TableList
[ WHERE Condition]
[ GROUP BY GroupingAttributeList ]
[ HAVING AggregateCondition ]
[ ORDER BY OrderingAttributeList ]
```

## Select, filter, order

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
The condition can be a complex logical expression containing AND, OR, LIKE.

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

Query two different tables
```sql
SELECT t1.FirstName, t1.Surname, t2.City
FROM Employee as t1, Department as t2
WHERE t1.DEpt = t2.DeptName
```

## Aggregate Functions

- AVG
- COUNT
- SUM
- MAX
- MIN

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

## Merging tables

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

