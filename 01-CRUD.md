# CRUD

Create, read, update, delete.

- [Managing tables](#managing-tables)
- [Querying data](#querying-data-from-one-or-more-tables)
  - [Aggregation](#aggregation-functions)
  - [Merge](#merging-tables)
- [Operators](#sql-operators)
- [Insert, Update, Delete](#insert-update-delete)


## Managing tables

Create a new table with three columns
```sql
CREATE TABLE t (
     id INT PRIMARY KEY,
     name VARCHAR NOT NULL,
     price INT DEFAULT 0
);
```

Delete the table from the database
```sql
DROP TABLE t ;
```

Add a new column to the table
```sql
ALTER TABLE t ADD column;
```

Drop column c from the table
```sql
ALTER TABLE t DROP COLUMN c ;
```

Add a constraint
```sql
ALTER TABLE t ADD constraint;
```

Drop a constraint
```sql
ALTER TABLE t DROP constraint;
```

Rename a table from t1 to t2
```sql
ALTER TABLE t1 RENAME TO t2;
```

Rename column c1 to c2
```sql
ALTER TABLE t1 RENAME c1 TO c2 ;
```

Remove all data in a table
```sql
TRUNCATE TABLE t;
```

Set c1 and c2 as a primary key
```sql
CREATE TABLE t(
    c1 INT, c2 INT, c3 VARCHAR,
    PRIMARY KEY (c1,c2)
);
```

Set c2 column as a foreign key
```sql
CREATE TABLE t1(
    c1 INT PRIMARY KEY,  
    c2 INT,
    FOREIGN KEY (c2) REFERENCES t2(c2)
);
```

Make the values in c1 and c2 unique
```sql
CREATE TABLE t(
    c1 INT, c1 INT,
    UNIQUE(c2,c3)
);
```

Ensure c1 > 0 and values in c1 >= c2
```sql
CREATE TABLE t(
  c1 INT, c2 INT,
  CHECK(c1> 0 AND c1 >= c2)
);
```

Set values in c2 column not NULL
```sql
CREATE TABLE t(
     c1 INT PRIMARY KEY,
     c2 VARCHAR NOT NULL
);
```

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

### Aggregate Functions

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

### Merging tables

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

## Insert, Update, Delete

Insert one row into a table
```sql
INSERT INTO t(column_list)
VALUES(value_list);
```

Insert multiple rows into a table
```sql
INSERT INTO t(column_list)
VALUES (value_list), 
       (value_list), …;
```

Insert rows from t2 into t1
```sql
INSERT INTO t1(column_list)
SELECT column_list
FROM t2;
```

Update new value in the column c1 for all rows
```sql
UPDATE t
SET c1 = new_value;
```

Update values in the column c1, c2 that match the condition
```sql
UPDATE t
SET c1 = new_value, 
        c2 = new_value
WHERE condition;
```

Delete all data in a table
```sql
DELETE FROM t;
```

Delete subset of rows in a table
```sql
DELETE FROM t
WHERE condition;
```