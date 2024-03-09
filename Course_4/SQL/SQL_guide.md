# Reference Guide: SQL

## Table of Contents

- [Query a Database](#query-a-database)
- [Apply Filters to SQL Queries](#apply-filters-to-sql-queries)
- [Join Tables](#join-tables)
- [Perform Calculations](#perform-calculations)

## Query a Database

### FROM

Indicates which table to query; required to perform a query

```sql
FROM employees
```

### ORDER BY

Sequences the records returned by a query based on a specified column or columns

```sql
ORDER BY department
ORDER BY department ASC
ORDER BY city DESC
ORDER BY country, city
```

### SELECT
Indicates which columns to return; required to perform a query

```sql
SELECT employee_id
SELECT *
```

## Apply Filters to SQL Queries

### AND
Specifies that both conditions must be met simultaneously in a filter that contains two conditions

```sql
WHERE region = 5 AND country = 'USA'
```

### BETWEEN
Filters for numbers or dates within a range; BETWEEN is followed by the first value to include in the range, the AND operator, and the last value to include in the range

```sql
WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01'
```
### = (equal to)

Used in filters to return only the records that contain a value in a specified column that is equal to a particular value

```sql
WHERE birthdate = '1980-05-15'
```
### > (greater than)
Used in filters to return only the records that contain a value in a specified column that is greater than a particular value

```sql
WHERE birthdate > '1970-01-01'
```
### >= (greater than or equal to)
Used in filters to return only the records that contain a value in a specified column that is greater than or equal to a particular value

```sql
WHERE birthdate >= '1965-06-30'
```
### < (less than)
Used in filters to return only the records that contain a value in a specified column that is less than a particular value

```sql
WHERE date < '2023-01-31'
```
### <= (less than or equal to)
Used in filters to return only the records that contain a value in a specified column that is less than or equal to a particular value

```sql
WHERE date <= '2020-12-31'
```

### LIKE
Used with WHERE to search for a pattern in a column

```sql
WHERE title LIKE 'IT%'
WHERE state LIKE 'N_'
```
### NOT
Negates a condition

```sql

WHERE NOT country = 'Mexico'
```
### <> (not equal to)
Used in filters to return only the records that contain a value in a specified column that is not equal to a particular value

```sql
WHERE date <> '2023-02-28'
WHERE date != '2023-05-14'
```

### OR
Specifies that either condition can be met in a filter that contains two conditions

```sql
WHERE country = 'Canada' OR country = 'USA'
```

## Join Tables
The following SQL keywords are used to join tables.

### FULL OUTER JOIN
Returns all records from both tables; the column used to join the tables is specified following FULL OUTER JOIN with syntax that includes ON and equal to (=)

```sql
SELECT *
FROM employees
FULL OUTER JOIN machines ON employees.device_id = machines.device_id;
```

### INNER JOIN
Returns records matching on a specified column that exists in more than one table; the column used to join the tables is specified following INNER JOIN with syntax that includes ON and equal to (=)

```sql
SELECT *
FROM employees
INNER JOIN machines ON employees.device_id = machines.device_id;
```

### LEFT JOIN
Returns all the records of the first table, but only returns records of the second table that match on a specified column; the first (or left) table appears directly after the keyword FROM; the column used to join the tables is specified following LEFT JOIN with syntax that includes ON and equal to (=)

```sql
SELECT *
FROM employees
LEFT JOIN machines ON employees.device_id = machines.device_id;
```

### RIGHT JOIN
Returns all of the records of the second table, but only returns records from the first table that match on a specified column; the second (or right) table appears directly after the RIGHT JOIN keyword; the column used to join the tables is specified following RIGHT JOIN with syntax that includes ON and equal to (=)

``` sql
SELECT *
FROM employees
RIGHT JOIN machines ON employees.device_id = machines.device_id;
```
## Perform Calculations
The following SQL keywords are aggregate functions and are helpful when performing calculations.

### AVG
Returns a single number that represents the average of the numerical data in a column; placed after SELECT

```sql
SELECT AVG(height)
```

### COUNT
Returns a single number that represents the number of records returned from a query; placed after SELECT

```sql
SELECT COUNT(firstname)
```
### SUM
Returns a single number that represents the sum of the numerical data in a column; placed after SELECT

```sql
SELECT SUM(cost)
```


