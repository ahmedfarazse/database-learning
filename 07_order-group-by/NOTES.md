# ORDER BY and GROUP BY

## 1. ORDER BY (Sorting Data)

The `ORDER BY` clause is used to sort the result set in ascending or descending order.

* **ASC (Ascending):** Default behavior. Sorts A-Z or 0-9.
* **DESC (Descending):** Sorts Z-A or 9-0.

**Syntax:**
```sql
SELECT column1, column2 
FROM table_name 
ORDER BY column1 ASC|DESC;
```

**Examples:**
```sql
-- Sort students alphabetically by name (A-Z)
SELECT * FROM students 
ORDER BY name ASC;

-- Show the most expensive products first (High to Low)
SELECT name, price FROM products 
ORDER BY price DESC;
```

---

## 2. GROUP BY (Summarizing Data)

The `GROUP BY` statement groups rows that have the same values into summary rows (like "find the number of customers in each country"). 

It is almost always used with **Aggregate Functions**:
* `COUNT()`: Counts the number of rows.
* `SUM()`: Adds up numerical values.
* `AVG()`: Calculates the average.
* `MAX()` / `MIN()`: Finds the highest/lowest value.

**Syntax:**
```sql
SELECT column_name, COUNT(column_name)
FROM table_name
GROUP BY column_name;
```

**Examples:**
```sql
-- Count how many students belong to each city
SELECT city, COUNT(id) 
FROM students 
GROUP BY city;

-- Find the total sales amount for each product category
SELECT category, SUM(price) 
FROM sales 
GROUP BY category;
```

---

## Interview Questions

* What is the default sorting order of the `ORDER BY` clause?
* Can you sort a table by a column that is not included in the `SELECT` list?
* Why do we use aggregate functions with `GROUP BY`?
* If you want to filter grouped data, which clause do you use? (Answer: The `HAVING` clause is used to filter groups, because `WHERE` cannot be used with aggregate functions).

---

## Quick Revision

* **ORDER BY** → Sorts rows (ASC or DESC).
* **GROUP BY** → Groups duplicate values into summary rows.
* **Aggregate Functions** → `COUNT()`, `SUM()`, `MAX()`, `MIN()`.