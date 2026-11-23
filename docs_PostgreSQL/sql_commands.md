# SQL Commands

## **1. Data Query Language (DQL)**

| SQL Statement | Description                       | Example                                                                               |
| ------------- | --------------------------------- | ------------------------------------------------------------------------------------- |
| `SELECT`      | Retrieve data from a table        | `SELECT * FROM employees;`                                                            |
| `DISTINCT`    | Retrieve unique values            | `SELECT DISTINCT department FROM employees;`                                          |
| `WHERE`       | Filter rows based on conditions   | `SELECT * FROM employees WHERE id = 1;`                                               |
| `ORDER BY`    | Sort query results                | `SELECT * FROM employees ORDER BY name ASC;`                                          |
| `GROUP BY`    | Group rows with the same values   | `SELECT department, COUNT(*) FROM employees GROUP BY department;`                     |
| `HAVING`      | Filter grouped results            | `SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > 5;` |
| `LIMIT`       | Limit the number of returned rows | `SELECT * FROM employees LIMIT 10;`                                                   |
| `OFFSET`      | Skip a specified number of rows   | `SELECT * FROM employees OFFSET 10;`                                                  |

## **2. Data Manipulation Language (DML)**

| SQL Statement            | Description                                                      | Example                                                                                                    |
| ------------------------ | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `INSERT INTO`            | Insert new rows into a table                                     | `INSERT INTO employees (id, name) VALUES (1, 'John');`                                                     |
| `UPDATE`                 | Modify existing rows                                             | `UPDATE employees SET name = 'Mike' WHERE id = 1;`                                                         |
| `DELETE`                 | Delete rows from a table                                         | `DELETE FROM employees WHERE id = 1;`                                                                      |
| `TRUNCATE`               | Remove all rows from a table                                     | `TRUNCATE TABLE employees;`                                                                                |
| `RETURNING`              | Return modified rows after INSERT, UPDATE, or DELETE             | `DELETE FROM employees WHERE id = 1 RETURNING *;`                                                          |
| `INSERT ... ON CONFLICT` | Insert or update rows when a uniqueness conflict occurs (UPSERT) | `INSERT INTO employees (id, name) VALUES (1, 'John') ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name;` |

## **3. Data Definition Language (DDL)**

| SQL Statement     | Description                        | Example                                                   |
| ----------------- | ---------------------------------- | --------------------------------------------------------- |
| `CREATE DATABASE` | Create a new database              | `CREATE DATABASE company;`                                |
| `DROP DATABASE`   | Delete a database                  | `DROP DATABASE company;`                                  |
| `CREATE TABLE`    | Create a new table                 | `CREATE TABLE employees (id INTEGER, name VARCHAR(100));` |
| `ALTER TABLE`     | Modify an existing table structure | `ALTER TABLE employees ADD COLUMN age INTEGER;`           |
| `DROP TABLE`      | Delete a table                     | `DROP TABLE employees;`                                   |
| `TRUNCATE TABLE`  | Remove all rows from a table       | `TRUNCATE TABLE employees;`                               |
| `CREATE INDEX`    | Create an index                    | `CREATE INDEX idx_employees_name ON employees (name);`    |
| `DROP INDEX`      | Delete an index                    | `DROP INDEX idx_employees_name;`                          |
| `CREATE VIEW`     | Create a view                      | `CREATE VIEW employee_view AS SELECT * FROM employees;`   |
| `DROP VIEW`       | Delete a view                      | `DROP VIEW employee_view;`                                |
| `CREATE SCHEMA`   | Create a schema                    | `CREATE SCHEMA accounting;`                               |
| `DROP SCHEMA`     | Delete a schema                    | `DROP SCHEMA accounting;`                                 |

## **4. Data Control Language (DCL)**

| SQL Statement | Description                          | Example                                     |
| ------------- | ------------------------------------ | ------------------------------------------- |
| `GRANT`       | Grant privileges to a user or role   | `GRANT SELECT ON employees TO app_user;`    |
| `REVOKE`      | Revoke previously granted privileges | `REVOKE SELECT ON employees FROM app_user;` |

## **5. Transaction Control Language (TCL)**

| SQL Statement           | Description                             | Example                               |
| ----------------------- | --------------------------------------- | ------------------------------------- |
| `BEGIN`                 | Start a transaction                     | `BEGIN;`                              |
| `COMMIT`                | Commit a transaction                    | `COMMIT;`                             |
| `ROLLBACK`              | Roll back a transaction                 | `ROLLBACK;`                           |
| `SAVEPOINT`             | Create a savepoint within a transaction | `SAVEPOINT my_savepoint;`             |
| `ROLLBACK TO SAVEPOINT` | Roll back to a specified savepoint      | `ROLLBACK TO SAVEPOINT my_savepoint;` |
| `RELEASE SAVEPOINT`     | Remove a savepoint                      | `RELEASE SAVEPOINT my_savepoint;`     |

## **6. Common SQL Operators and Conditions**

| Operator / Condition | Description                                             | Example                                        |
| -------------------- | ------------------------------------------------------- | ---------------------------------------------- |
| `=`                  | Equal to                                                | `WHERE id = 1`                                 |
| `<>`                 | Not equal to                                            | `WHERE id <> 1`                                |
| `>`                  | Greater than                                            | `WHERE age > 20`                               |
| `<`                  | Less than                                               | `WHERE age < 30`                               |
| `>=`                 | Greater than or equal to                                | `WHERE age >= 20`                              |
| `<=`                 | Less than or equal to                                   | `WHERE age <= 30`                              |
| `AND`                | Combine multiple conditions (all must be true)          | `WHERE age > 20 AND age < 30`                  |
| `OR`                 | Combine multiple conditions (at least one must be true) | `WHERE department = 'IT' OR department = 'HR'` |
| `NOT`                | Negate a condition                                      | `WHERE NOT active`                             |
| `IN`                 | Match any value in a list                               | `WHERE id IN (1, 2, 3)`                        |
| `BETWEEN`            | Match a value within a range                            | `WHERE age BETWEEN 20 AND 30`                  |
| `LIKE`               | Pattern matching                                        | `WHERE name LIKE 'A%'`                         |
| `ILIKE`              | Case-insensitive pattern matching (PostgreSQL-specific) | `WHERE name ILIKE 'a%'`                        |
| `IS NULL`            | Check for NULL values                                   | `WHERE email IS NULL`                          |
| `IS NOT NULL`        | Check for non-NULL values                               | `WHERE email IS NOT NULL`                      |
| `EXISTS`             | Check whether a subquery returns any rows               | `WHERE EXISTS (SELECT 1 FROM departments)`     |

## **7. Common SQL Functions**

| Function            | Description                              | Example                                         |
| ------------------- | ---------------------------------------- | ----------------------------------------------- |
| `COUNT()`           | Count rows                               | `SELECT COUNT(*) FROM employees;`               |
| `SUM()`             | Calculate the sum                        | `SELECT SUM(salary) FROM employees;`            |
| `AVG()`             | Calculate the average                    | `SELECT AVG(salary) FROM employees;`            |
| `MAX()`             | Get the maximum value                    | `SELECT MAX(salary) FROM employees;`            |
| `MIN()`             | Get the minimum value                    | `SELECT MIN(salary) FROM employees;`            |
| `COALESCE()`        | Return the first non-NULL value          | `SELECT COALESCE(email, 'N/A') FROM employees;` |
| `NULLIF()`          | Return NULL if two expressions are equal | `SELECT NULLIF(value, 0) FROM measurements;`    |
| `CURRENT_DATE`      | Get the current date                     | `SELECT CURRENT_DATE;`                          |
| `CURRENT_TIMESTAMP` | Get the current date and time            | `SELECT CURRENT_TIMESTAMP;`                     |
