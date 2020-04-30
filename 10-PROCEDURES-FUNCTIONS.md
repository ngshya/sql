# Procedure

```bash
DELIMITER $$
    CREATE PROCEDURE myProcedure2(book_id int)
        BEGIN
            SELECT name FROM book WHERE id = book_id;
        END;
;
```

```bash
CALL myProcedure2(3);
```

# Function
```bash
CREATE 
[ DEFINER = { CURRENT-USER | username } ] 
FUNCTION function-name [(parameter datatype [, parameter datatype]) ]
RETURNS datatype [LANGUAGE SQL
                        | DETERMINISTIC
                        | NOT DETERMINISTIC
                        | {CONTAINS SQL 
                          | NO SQL
                          | READS SQL DATA
                          | MODIFIES SQL DATA}
                        | SQL SECURITY {DEFINER | INVOKER}
                        | COMMENT 'comment'

BEGIN

   declaration-section

   executable-section

END;
```

```bash
DELIMITER //

CREATE FUNCTION sumFunc (x INT )
RETURNS INT DETERMINISTIC

BEGIN

   DECLARE sum INT;
   SET sum = 0;
   label1: WHILE sum <= 3000 DO
   SET sum = sum + x;
   END WHILE label1;
   RETURN sum;
END; //
DELIMITER ;
```

```bash
select sumFunc(1000);
```

```bash
DROP FUNCTION function_name;
```
