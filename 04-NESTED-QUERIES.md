# Nested Queries

```sql
SELECT FirstName, Surname
FROM EMPLOYEE
WHERE Dept = ANY (SELECT DeptName
                  FROM Department
                  WHERE City = 'London')
```

```sql
SELECT FirstName, Surname
FROM EMPLOYEE
WHERE Dept <> ALL (SELECT DeptName
                   FROM Department
                   WHERE City = 'London')
```

```sql
SELECT FirstName, Surname
FROM EMPLOYEE
WHERE Dept IN (SELECT DeptName
               FROM Department
               WHERE City = 'London')
```

```sql
SELECT FirstName, Surname
FROM EMPLOYEE
WHERE Dept NOT IN (SELECT DeptName
                   FROM Department
                   WHERE City = 'London')
```

```sql
SELECT Dept
FROM Employee
WHERE Salary >= ALL (SELECT Salary
                     FROM Employee)
```

```sql
SELECT *
FROM Person P
WHERE EXISTS (SELECT * 
              FROM Person P1
              WHERE P1.FirstName = P.FirstName 
              AND P1.Surname = P.Surname
              AND P1.TaxCode <> P.TaxCode)
```
