
# 📘 SQL Cheat Sheet (MySQL)

## 1. 🗄️ Database Basics

```sql
-- Show all databases
SHOW DATABASES;

-- Create a database
CREATE DATABASE company;

-- Create database if it doesn't exist
CREATE DATABASE IF NOT EXISTS company;

-- Select a database
USE company;

-- Show currently selected database
SELECT DATABASE();

-- Delete a database
DROP DATABASE company;

-- Delete database if it exists
DROP DATABASE IF EXISTS company;
```

## 2. 🔤 MySQL Data Types

| Data Type | Description | Example |
|---|---|---|
| `INT` | Whole numbers | `100` |
| `BIGINT` | Large whole numbers | `9876543210` |
| `DECIMAL(p,s)` | Exact decimal values | `9999.99` |
| `FLOAT` | Approximate decimal values | `10.5` |
| `CHAR(n)` | Fixed-length string | `'ABC'` |
| `VARCHAR(n)` | Variable-length string | `'Pawan'` |
| `TEXT` | Long text | Article content |
| `DATE` | Date | `'2026-11-12'` |
| `DATETIME` | Date and time | `'2026-11-12 14:30:00'` |
| `BOOLEAN` | True/False (`1`/`0`) | `TRUE` |


## 3. 📋 Table Creation & Structure (DDL)

```sql
-- Create a table
CREATE TABLE employees (
    id INT,
    name VARCHAR(100),
    email VARCHAR(100),
    salary DECIMAL(10,2)
);

-- Show all tables
SHOW TABLES;

-- Describe table structure
DESC employees;

-- Show complete table creation statement
SHOW CREATE TABLE employees;

-- Add a column
ALTER TABLE employees
ADD COLUMN age INT;

-- Modify a column datatype
ALTER TABLE employees
MODIFY COLUMN name VARCHAR(150);

-- Rename a column
ALTER TABLE employees
RENAME COLUMN name TO full_name;

-- Drop a column
ALTER TABLE employees
DROP COLUMN age;

-- Rename a table
RENAME TABLE employees TO staff;

-- Delete a table
DROP TABLE staff;
```

## 4. 🔑 Constraints

Constraints are rules applied to table columns to maintain data accuracy and integrity.

| Constraint | Description |
|---|---|
| `PRIMARY KEY` | Uniquely identifies each row |
| `FOREIGN KEY` | Establishes a relationship between tables |
| `UNIQUE` | Prevents duplicate values |
| `NOT NULL` | Prevents NULL values |
| `DEFAULT` | Assigns a default value |
| `CHECK` | Validates a condition |
| `AUTO_INCREMENT` | Automatically generates numeric values |

```sql
-- Create table with constraints
CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    salary DECIMAL(10,2) DEFAULT 0,
    age INT CHECK (age >= 18),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(id)
);
```

## 5. ✏️ Data Manipulation (DML)

```sql
-- Insert a single record
INSERT INTO employees (name, email, salary)
VALUES ('Pawan', 'pawan@gmail.com', 50000);

-- Insert multiple records
INSERT INTO employees (name, email, salary)
VALUES
('Rahul', 'rahul@gmail.com', 40000),
('Amit', 'amit@gmail.com', 45000);

-- Update records
UPDATE employees
SET salary = 60000
WHERE id = 1;

-- Delete specific records
DELETE FROM employees
WHERE id = 1;
```



## 6. 🔍 Data Retrieval (SELECT)

```sql
-- Select all columns
SELECT * FROM employees;

-- Select specific columns
SELECT name, salary FROM employees;

-- Select distinct values
SELECT DISTINCT department_id FROM employees;

-- Use column aliases
SELECT name AS employee_name FROM employees;

-- Limit the number of records
SELECT * FROM employees LIMIT 5;

-- Skip records using OFFSET
SELECT * FROM employees LIMIT 5 OFFSET 10;
```

## 7. ⚖️ Operators & Conditions

```sql
-- Comparison operators: =, !=, <>, >, <, >=, <=

SELECT * FROM employees WHERE salary > 30000;

-- Logical operators
SELECT * FROM employees
WHERE salary > 30000 AND age >= 25;

SELECT * FROM employees
WHERE department_id = 1 OR department_id = 2;

SELECT * FROM employees
WHERE NOT department_id = 1;

-- BETWEEN
SELECT * FROM employees
WHERE salary BETWEEN 30000 AND 60000;

-- IN
SELECT * FROM employees
WHERE department_id IN (1, 2, 3);

-- NOT IN
SELECT * FROM employees
WHERE department_id NOT IN (1, 2);

-- LIKE
SELECT * FROM employees WHERE name LIKE 'P%';

-- IS NULL
SELECT * FROM employees WHERE department_id IS NULL;

-- IS NOT NULL
SELECT * FROM employees WHERE department_id IS NOT NULL;
```

**LIKE Wildcards:**
- `%` : Matches zero or more characters.
- `_` : Matches exactly one character.

## 8. 🔃 Sorting & Grouping

```sql
-- Ascending order
SELECT * FROM employees ORDER BY salary ASC;

-- Descending order
SELECT * FROM employees ORDER BY salary DESC;

-- Sort using multiple columns
SELECT * FROM employees
ORDER BY department_id ASC, salary DESC;

-- Group records
SELECT department_id, COUNT(*)
FROM employees
GROUP BY department_id;

-- Filter grouped records
SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id
HAVING AVG(salary) > 40000;
```

## 9. 📊 Aggregate Functions

Aggregate functions perform calculations on multiple rows and return a single result per group.

```sql
-- Count records
SELECT COUNT(*) FROM employees;

-- Sum of salaries
SELECT SUM(salary) FROM employees;

-- Average salary
SELECT AVG(salary) FROM employees;

-- Minimum salary
SELECT MIN(salary) FROM employees;

-- Maximum salary
SELECT MAX(salary) FROM employees;

-- Count distinct departments
SELECT COUNT(DISTINCT department_id)
FROM employees;
```

## 10. 🔗 SQL Joins

Joins are used to retrieve data from multiple related tables.

```sql
-- INNER JOIN: Returns matching records from both tables
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.id;

-- LEFT JOIN: Returns all records from left table
-- and matching records from right table
SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.id;

-- RIGHT JOIN: Returns all records from right table
-- and matching records from left table
SELECT e.name, d.department_name
FROM employees e
RIGHT JOIN departments d
ON e.department_id = d.id;

-- CROSS JOIN: Returns Cartesian product
SELECT e.name, d.department_name
FROM employees e
CROSS JOIN departments d;

-- SELF JOIN: Join a table with itself
SELECT e.name AS employee, m.name AS manager
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.id;
```

## 11. 🔍 Subqueries

A subquery is a query nested inside another SQL query.

```sql
-- Subquery with WHERE
SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary) FROM employees
);

-- Subquery with IN
SELECT *
FROM employees
WHERE department_id IN (
    SELECT id FROM departments
    WHERE department_name = 'IT'
);

-- EXISTS
SELECT *
FROM departments d
WHERE EXISTS (
    SELECT 1 FROM employees e
    WHERE e.department_id = d.id
);

-- NOT EXISTS
SELECT *
FROM departments d
WHERE NOT EXISTS (
    SELECT 1 FROM employees e
    WHERE e.department_id = d.id
);
```

## 12. 🔀 Set Operations

Set operations combine the results of multiple SELECT queries.

```sql
-- UNION: Combines results and removes duplicates
SELECT name FROM employees
UNION
SELECT name FROM managers;

-- UNION ALL: Combines results and keeps duplicates
SELECT name FROM employees
UNION ALL
SELECT name FROM managers;
```

## 13. ⚙️ SQL Functions

### String Functions

```sql
-- Combine strings
SELECT CONCAT('Hello', ' ', 'World');

-- Convert to uppercase
SELECT UPPER('pawan');

-- Convert to lowercase
SELECT LOWER('PAWAN');

-- Find string length in bytes
SELECT LENGTH('Pawan');

-- Remove leading and trailing spaces
SELECT TRIM('  Pawan  ');

-- Extract part of a string
SELECT SUBSTRING('Pawan Kumar', 1, 5);
```

### Numeric Functions

```sql
-- Round a number
SELECT ROUND(123.456, 2);

-- Round up
SELECT CEIL(10.2);

-- Round down
SELECT FLOOR(10.8);

-- Absolute value
SELECT ABS(-100);
```

### Date Functions

```sql
-- Current date
SELECT CURDATE();

-- Current date and time
SELECT NOW();

-- Difference between two dates in days
SELECT DATEDIFF('2026-12-01', '2026-11-12');

-- Add days to a date
SELECT DATE_ADD(CURDATE(), INTERVAL 7 DAY);

-- Subtract days from a date
SELECT DATE_SUB(CURDATE(), INTERVAL 7 DAY);
```

### Conditional Functions

```sql
-- IF
SELECT IF(salary > 50000, 'High', 'Low')
FROM employees;

-- IFNULL
SELECT IFNULL(department_id, 0)
FROM employees;

-- COALESCE: Returns the first non-NULL value
SELECT COALESCE(phone, email, 'Not Available')
FROM employees;

-- CASE WHEN
SELECT name,
    CASE
        WHEN salary >= 60000 THEN 'High'
        WHEN salary >= 40000 THEN 'Medium'
        ELSE 'Low'
    END AS salary_category
FROM employees;
```

## 14. 🔄 Transactions (TCL)

Transactions ensure that a group of SQL operations is executed reliably.

```sql
-- Start a transaction
START TRANSACTION;

-- Perform operations
UPDATE employees
SET salary = salary + 5000
WHERE id = 1;

-- Save changes permanently
COMMIT;

-- Undo uncommitted changes
ROLLBACK;

-- Create a savepoint
SAVEPOINT sp1;

-- Roll back to a savepoint
ROLLBACK TO SAVEPOINT sp1;

-- Remove a savepoint
RELEASE SAVEPOINT sp1;
```

**Important Notes:**
- `COMMIT`: Permanently saves transaction changes.
- `ROLLBACK`: Undoes uncommitted changes.
- `SAVEPOINT`: Creates a point to which you can roll back.

