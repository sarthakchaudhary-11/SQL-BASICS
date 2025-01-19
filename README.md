Interactive SQL Guide

This interactive README introduces key SQL concepts and commands. Use this guide to practice SQL operations step-by-step with examples.

1. Creating a Table

Use the CREATE TABLE command to define a new table.

Command:

CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint
);

Example:

CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Department VARCHAR(50),
    Salary DECIMAL(10, 2)
);

Interactive Task:

Create a table named Products with columns: ProductID (INT, PRIMARY KEY), ProductName (VARCHAR(100), NOT NULL), and Price (DECIMAL(8, 2)).

2. Dropping a Table

Use DROP TABLE to permanently delete a table and its data.

Command:

DROP TABLE table_name;

Example:

DROP TABLE Employees;

Interactive Task:

Drop the Products table you created earlier.

3. Altering a Table

Modify an existing table using the ALTER TABLE command.

Add a New Column:

ALTER TABLE table_name
ADD column_name datatype;

Example:

ALTER TABLE Employees
ADD Age INT;

Modify an Existing Column:

ALTER TABLE table_name
MODIFY column_name new_datatype;

Example:

ALTER TABLE Employees
MODIFY Salary DECIMAL(12, 2);

Drop a Column:

ALTER TABLE table_name
DROP COLUMN column_name;

Example:

ALTER TABLE Employees
DROP COLUMN Age;

Interactive Task:

Add a column JoinDate (DATE) to the Employees table.

Modify the Salary column to DECIMAL(15, 2).

Drop the Age column.

4. Constraints

Constraints enforce rules on table data.

Common Constraints:

PRIMARY KEY: Ensures unique identification of each row.

FOREIGN KEY: Links two tables.

NOT NULL: Prevents NULL values.

UNIQUE: Ensures column values are unique.

CHECK: Enforces a condition.

DEFAULT: Sets a default value.

Example:

CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    ProductName VARCHAR(50) NOT NULL,
    Quantity INT CHECK (Quantity > 0),
    OrderDate DATE DEFAULT GETDATE()
);

Interactive Task:

Create a table Customers with constraints: CustomerID (INT, PRIMARY KEY), CustomerName (VARCHAR(100), NOT NULL), and City (VARCHAR(50), DEFAULT 'Unknown').

5. Querying Data

Order By

Sort results in ascending or descending order.

SELECT column1, column2
FROM table_name
ORDER BY column_name [ASC|DESC];

Example:

SELECT * FROM Employees
ORDER BY Salary DESC;

Interactive Task:

Query the Employees table and order the results by Department in ascending order.

Where Clause

Filter rows based on a condition.

SELECT column1, column2
FROM table_name
WHERE condition;

Example:

SELECT * FROM Employees
WHERE Department = 'HR';

Interactive Task:

Query the Employees table to find rows where Salary > 50000.

Having Clause

Filter grouped rows.

SELECT column1, COUNT(column2)
FROM table_name
GROUP BY column1
HAVING COUNT(column2) > value;

Example:

SELECT Department, COUNT(EmployeeID)
FROM Employees
GROUP BY Department
HAVING COUNT(EmployeeID) > 5;

Interactive Task:

Group Employees by Department and filter groups where the count of employees exceeds 3.

6. Using Functions

Round Function

Round numerical values to a specific number of decimal places.

SELECT ROUND(column_name, decimals)
FROM table_name;

Example:

SELECT ROUND(Salary, 2)
FROM Employees;

Interactive Task:

Query the Employees table and round Salary values to 1 decimal place.

7. Limiting Results

Limit

Restrict the number of rows returned.

SELECT column1, column2
FROM table_name
LIMIT number;

Example:

SELECT * FROM Employees
LIMIT 5;

Offset

Skip rows before returning results.

SELECT column1, column2
FROM table_name
LIMIT number OFFSET offset_value;

Example:

SELECT * FROM Employees
LIMIT 5 OFFSET 10;

Interactive Task:

Query the Employees table to return 5 rows, skipping the first 2 rows.


