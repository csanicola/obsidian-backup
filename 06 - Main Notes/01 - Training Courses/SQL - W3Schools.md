---
Created Date: September 11th, 2024 04:39 PM
page-tags: "[[sql]]"
tags:
  - currently-working-on
  - tutorial
cssclasses:
---
# SQL - W3Schools

Course: [W3Schools](https://www.w3schools.com/sql)

# Intro

- SQL = Structured Query Language
- RDBMS = Relational Database Mangement System
  - basis for SQL and modern database systems are MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access
  - data in these databases are stored as tables consisting of columns and rows

_Example of looking up a table of data in SQL:_

```sql
SELECT * FROM Customers;
```

- **fields** = columns and are what the data in the tables are broken up by
- SQL keywords are NOT case sensitive so `select` is the same as `SELECT`

# Syntax

- **SQL Statements** = the code you use to perform actions on the database

_Example of selecting all records from the Customers table:_

```sql
SELECT * FROM Customers;
```

- **records** = the rows in the database tables
- **semicolons** = seperate each SQL statement

**Some of the Most Important SQL Commands**

- `SELECT` - extracts data from a database
- `UPDATE` - updates data in a database
- `DELETE` - deletes data from a database
- `INSERT INTO` - inserts new data into a database
- `CREATE DATABASE` - creates a new database
- `ALTER DATABASE` - modifies a database
- `CREATE TABLE` - creates a new table
- `ALTER TABLE` - modifies a table
- `DROP TABLE` - deletes a table
- `CREATE INDEX` - creates an index (search key)
- `DROP INDEX` - deletes an index

# SELECT

Syntax:

```sql
SELECT column1, column2, ...
FROM table_name;
```

**column1, column2** = the field names from the table that you want to pull data from

**table_name** = the name of the table you want to pull the data from

- to select ALL the columns from a table you use the `SELECT *` syntax
  - Ex: `SELECT * FROM Customers;`

# SELECT DISTINCT

Syntax:

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

- `SELECT DISTINCT` will only return the distinct (different) values from a table
- Ex: `SELECT DISTINCT Country FROM Customers;` - this will only show the unique country's from the customers table

## Count Distinct

- in order to get a count for how many distinct values are in the data you would use the following syntax:

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```

_This syntax however, is not supported in Microsoft Access databases so you would do the following workaround:_

```sql
SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```

# WHERE Clause
- `WHERE` is used to filter records that meet specific conditions
*Example: Select all customers from Mexico*
``` SQL
SELECT * FROM Customers
WHERE Country='Mexico';
```
Syntax:
```SQL
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
- the `WHERE` clause can also be used in `UPDATE`, `DELETE`, etc.
## Text vs. Numeric
- **Text** requires single quotes but **numeric** values do not
*Example:*
```SQL
SELECT * FROM Customers
WHERE CustomerID=1;
```

**Operators Used with WHERE**
```SQL
= - Equal
> - Greater than
< - Less than
>= - Greater than or equal
<= - Less than or equal
<> Not euqal (but some versions use !=)
BETWEEN - between a certain range
LIKE - search for a pattern
IN - to specify multiple possible values for a column
```
# ORDER BY
- `ORDER BY` is used to sort the result-set in ascending or descending order
*Example: Sort the products by price*
```SQL
SELECT * FROM Products
ORDER BY Price;
```
Syntax:
```SQL
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```
## DESC
- sorts records in **descending** order
*Example: Sort the products from highest to lowest price*
```SQL
SELECT * FROM Products
ORDER BY Price DESC;
```

## Order Alphabetically
- string values will sort alphabetically with `ORDER BY`
*Example: sorting the products alphabetically by ProductName*
```SQL
SELECT * FROM Products
ORDER BY ProductName;
```
*Example: sorting the products by ProductName in reverse order:*
```SQL
SELECT * FROM Products
ORDER BY ProductName DESC;
```
## Order by Several Columns
*Example:*
```SQL
SELECT * FROM Customers
ORDER BY Country, CustomerName;
```
*Example: sort Country by ascending and CustomerName by descending*
```SQL
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

# AND 
- The `WHERE` clause can contain one or many `AND` operators.
- The `AND` operator is used to filter records based on more than one condition 
*Example: Select all customers from Spain that starts with the letter ‘G’*
```SQL
SELECT *
FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
```
*Syntax:*
```SQL
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

## AND vs OR
- The `AND` operator displays a record if *all* the conditions are TRUE
- The `OR` operator displays a record if *any* of the conditions are TRUE
*Example: The following SQL statement selects all fields from `Customers` where `Country` is “Germany” AND `City` is “Berlin” AND `PostalCode` is higher than 12000*
```SQL
SELECT * FROM Customers
WHERE Country = 'Germany'
AND City = 'Berlin'
AND PostalCode > 12000;
```

## Combining AND and OR
- You can combine the `AND` and `OR` operators.
*Example: The following SQL statement selects all customers from Spain that starts with a “G” or an “R”*
```SQL
SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```

# OR
- The `WHERE` clause can contain one or more `OR` operators
- The `OR` operator is used to filter records based on more than one condition 
*Example: Select all customers from Germany or Spain*
```SQL
SELECT * 
FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';
```
*Syntax:*
```SQL
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```
## OR vs AND 
- The `OR` operator displays a record if *any* of the conditions are TRUE
- The `AND` operator displays a record if *all* the conditions are TRUE

# NOT
- The `NOT` operator is used in combination with other operators to give 









---
# References



