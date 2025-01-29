# Basic SQL Guide

## Overview
This guide covers fundamental SQL operations including creating tables, modifying structures, applying constraints, using functions, and limiting query results.

## Table of Contents
- [Creating a Table](#creating-a-table)
- [Dropping a Table](#dropping-a-table)
- [Altering a Table](#altering-a-table)
- [SQL Constraints](#sql-constraints)
- [Using Functions](#using-functions)
- [Limit and Offset](#limit-and-offset)
- [Additional Resources](#additional-resources)


## Creating a Table
Use the `CREATE TABLE` statement to define a new table:
```sql
CREATE TABLE Employees (
    ID INT PRIMARY KEY,
    Name VARCHAR(100),
    Age INT,
    Salary DECIMAL(10,2)
);
```

## Dropping a Table
To remove an existing table:
```sql
DROP TABLE Employees;
```

## Altering a Table
Modify an existing table by adding or removing columns:
```sql
ALTER TABLE Employees ADD COLUMN Department VARCHAR(50);
ALTER TABLE Employees DROP COLUMN Age;
```

## SQL Constraints
Constraints enforce rules on the data:
- `PRIMARY KEY`: Uniquely identifies each row.
- `FOREIGN KEY`: Establishes relationships between tables.
- `UNIQUE`: Ensures all values in a column are unique.
- `NOT NULL`: Prevents null values in a column.
- `CHECK`: Validates conditions before inserting data.

Example:
```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    OrderDate DATE,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

## Using Functions
SQL functions perform operations on data:
```sql
SELECT COUNT(*) FROM Employees; -- Count the number of employees
SELECT AVG(Salary) FROM Employees; -- Calculate average salary
SELECT UPPER(Name) FROM Employees; -- Convert names to uppercase
```

## Limit and Offset
Control the number of records returned using `LIMIT` and `OFFSET`:
```sql
SELECT * FROM Employees LIMIT 5; -- Get the first 5 employees
SELECT * FROM Employees LIMIT 5 OFFSET 10; -- Skip the first 10 and get the next 5
```

---

## 🔗 Additional Resources
- [SQL Documentation](https://www.w3schools.com/sql/)
- [SQL Operators](https://www.sqltutorial.org/sql-operators/)
- [Advanced SQL Queries](https://mode.com/sql-tutorial/)



