# MariaDB Data Types

## String Data Types

| String Data Type | Description |
| :---- | :---- |
| char(size) | The size denotes the number of characters to be stored. It stores a maximum of 255 characters. Fixed-length strings. |
| varchar(size) | The size denotes the number of characters to be stored. It stores a maximum of 255 characters. Variable-length strings. |
| text(size) | The size denotes the number of characters to be stored. It stores a maximum of 255 characters. Fixed-length strings. |
| binary(size) | The size denotes the number of characters to be stored. It stores a maximum of 255 characters. Fixed-size strings. |

## Numeric Data Types

|Numeric Data Types | Description |
| :---- | :---- |
|bit | A very small integer value equivalent to tinyint(1). Signed values range between -128 and 127. Unsigned values range between 0 and 255. |
|int(m) | A standard integer value. Signed values range between -2147483648 and 2147483647. Unsigned values range between 0 and 4294967295. |
|float(m, d) | A floating point number with single precision. |
|double(m,d) | A floating point number with double precision.|
|float(p) | A floating point number. |

## Date/Time Data Types

| Date/Time Data Type | Description |
| :---- | :---- |
| Date | Displayed in the form 'yyyy-mm-dd.' Values range between '1000-01-01' and '9999-12-31'. |
| Datetime | Displayed in the form 'yyyy-mm-dd hh:mm:ss'. Values range between '1000-01-01 00:00:00' and '9999-12-31 23:59:59'. |
| timestamp(m) | Displayed in the form 'yyyy-mm-dd hh:mm:ss'. Values range between '1970-01-01 00:00:01' utc and '2038-01-19 03:14:07' utc. |
| Time | Displayed in the form 'hh:mm:ss'. Values range between '-838:59:59' and '838:59:59'. |

## Large Object Datatypes (LOB)

| Large object Datatype | Description |
| :---- | :---- |
| tinyblob | Its maximum size is 255 bytes. |
| blob(size) | Takes 65,535 bytes as the maximum size. |
| mediumblob | Its maximum size is 16,777,215 bytes. |
| longtext | It takes 4GB as the maximum size. |
