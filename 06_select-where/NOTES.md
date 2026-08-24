# SELECT and WHERE Clauses

## Introduction

Retrieving data efficiently means only asking the database for exactly what you need. 
* **`SELECT`** determines which **columns** to return.
* **`WHERE`** determines which **rows** to return based on specific conditions.

---

## The Basic Syntax

```sql
SELECT column1, column2 
FROM table_name 
WHERE condition;
```

---

## Common Operators Used with WHERE

### 1. Equality and Comparison
* **`=` (Equal to):** Exact match.
  ```sql
  SELECT * FROM students WHERE city = 'Lahore';
  ```
* **`!=` or `<>` (Not equal to):** Excludes a value.
  ```sql
  SELECT * FROM students WHERE city != 'Karachi';
  ```
* **`>` / `<` / `>=` / `<=` (Greater/Less than):** For numbers and dates.
  ```sql
  SELECT name FROM products WHERE price > 5000;
  ```

### 2. Logical Operators
* **`AND`:** Both conditions must be true.
  ```sql
  SELECT * FROM users WHERE age > 18 AND status = 'active';
  ```
* **`OR`:** At least one condition must be true.
  ```sql
  SELECT * FROM users WHERE city = 'Okara' OR city = 'Lahore';
  ```

### 3. Advanced Filtering
* **`IN`:** Checks if a value matches any value in a list.
  ```sql
  SELECT * FROM products WHERE category IN ('Electronics', 'Clothing', 'Toys');
  ```
* **`LIKE`:** Used for pattern matching (Search functionality).
  * `%` represents zero, one, or multiple characters.
  ```sql
  -- Finds names starting with 'A'
  SELECT * FROM students WHERE name LIKE 'A%'; 
  
  -- Finds names ending with 'khan'
  SELECT * FROM students WHERE name LIKE '%khan';
  ```

---

## Interview Questions

* What is the primary purpose of the `WHERE` clause?
* What is the difference between `=` and `LIKE`?
* How would you retrieve all records where the price is between 100 and 500? (Hint: You can use `price >= 100 AND price <= 500` or the `BETWEEN` operator).
* Why do string values in SQL queries need single quotes, while numbers do not?

---

## Quick Revision

* **Columns Filter** → Managed by `SELECT`.
* **Rows Filter** → Managed by `WHERE`.
* Quotes (`' '`) → Required for Text/String data. Not required for numbers.
* `AND` / `OR` → Used to chain multiple conditions together.