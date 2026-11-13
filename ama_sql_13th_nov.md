
# 📚 SQL AMA 13th NOVEMBER

## 1. Difference between WHERE and HAVING
- `WHERE`: Filters rows before grouping.
- `HAVING`: Filters groups after `GROUP BY`.

## 2. Difference between COUNT(*) and COUNT(column_name)
- `COUNT(*)`: Counts all rows, including rows containing NULL values.
- `COUNT(column_name)`: Counts only non-NULL values in that column.

## 3. Will DISTINCT remove NULL values?
No. `DISTINCT` does not remove NULL values. It returns only one NULL if multiple NULL values exist.

## 4. Command to sort records in descending order
Use `ORDER BY` with `DESC`.

```sql
SELECT * FROM employees
ORDER BY salary DESC;
```

## 5. How many types of JOINs are there in SQL?
Commonly, there are 5 types:
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- CROSS JOIN
- SELF JOIN

## 6. What is 1NF (First Normal Form)?
A table is in 1NF if:
- Each column contains atomic (single) values.
- There are no repeating groups or multiple values in a single cell.
- Each row can be uniquely identified.

## 7. Difference between INNER JOIN and LEFT JOIN
- `INNER JOIN`: Returns only matching records from both tables.
- `LEFT JOIN`: Returns all records from the left table and matching records from the right table. Unmatched right-side values are NULL.

## 8. What is Normalization?
Normalization is the process of organizing data into multiple related tables to reduce data redundancy and improve data integrity.

## 9. How to add a new column to a table?
Use `ALTER TABLE` with `ADD COLUMN`.

```sql
ALTER TABLE employees
ADD COLUMN age INT;
```

## 10. Can we use WHERE after GROUP BY?
No. `WHERE` must come before `GROUP BY`. To filter grouped results, use `HAVING`.

## 11. What is the use of RANK() function?
`RANK()` assigns ranks to rows based on the specified ordering. Rows with the same value get the same rank, and the next rank is skipped.

```sql
SELECT name, salary,
RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;
```

## 12. What happens if we use DELETE without WHERE?
All rows from the table will be deleted, but the table structure remains unchanged.

```sql
DELETE FROM employees;
```

## 13. What is an INDEX in SQL?
An index is a data structure that helps retrieve records faster from a table. It improves read performance but can slow down INSERT, UPDATE and DELETE operations.

## 14. Difference between SUM() and COUNT()
- `SUM()`: Returns the total of numeric values, ignoring NULL values.
- `COUNT()`: Returns the number of rows or non-NULL values, depending on the argument.

## 15. Which is faster: TRUNCATE or DELETE?
- `TRUNCATE` is generally faster because it removes all rows without processing them individually.
- `DELETE` removes rows individually and supports filtering using `WHERE`.
- `TRUNCATE` does not support `WHERE`, while `DELETE` does.

## 16. Which executes first: FROM, WHERE or SELECT?
Logical SQL query execution order:
1. `FROM` – Identifies the source tables.
2. `WHERE` – Filters rows.
3. `SELECT` – Selects the required columns.

## 17. Explain DML commands.
DML stands for Data Manipulation Language. It is used to manipulate data stored in tables.

Common DML commands:
- `INSERT`: Adds new records.
- `UPDATE`: Modifies existing records.
- `DELETE`: Removes records.
