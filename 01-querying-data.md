# Querying Data From Tables

## Querying data from a table

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

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```

```sql
```
