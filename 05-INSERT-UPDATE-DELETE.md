# Insert, Update, Delete

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
