# Managing tables

## Create or Drop Tables

General syntax
```sql
CREATE TABLE TableName(
  AttributeName Domain [ DefaultValue ] [ Constraints ]
  {, AttributeName Domain [ DefaultValue ] [ Constraints ] }
  [ OtherConstraints ]
)
```
The constraints could be also intra-relational (es. unique(FirstName, Surname)).

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

Remove all data in a table
```sql
TRUNCATE TABLE t;
```

## Constraints and Reaction Policies

Add a constraint
```sql
ALTER TABLE t ADD constraint;
```

Drop a constraint
```sql
ALTER TABLE t DROP constraint;
```

You can aso use CHECK to express arbitrary constraints during the schema definition and ASSERTIONS to define the constrains outside of the table definitions.

Reaction policies
```sql
CREATE TABLE Employee(
  FirstName character(20) NOT NULL,
  Surname character(20) NOT NULL,
  Dept char(20) NOT NULL,
  PRIMARY KEY(RegNo),
  FOREIGN KEY (Dept)
    REFERENCES DEpartment(DeptName), 
    ON DELETE SET NULL,
    ON UPDATE CASCADE,
  UNIQUE(FirstName Surname)
)
```

## Renaming

Rename a table from t1 to t2
```sql
ALTER TABLE t1 RENAME TO t2;
```

Rename column c1 to c2
```sql
ALTER TABLE t1 RENAME c1 TO c2 ;
```

### Set Keys

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

## Set Indexes

Create an index on c1 and c2 of the t table
```sql
CREATE INDEX idx_name 
ON t(c1,c2);
```

Create a unique index on c3, c4 of the t table
```sql
CREATE UNIQUE INDEX idx_name
ON t(c3,c4)
```

Drop an index
```sql
DROP INDEX idx_name;
```
