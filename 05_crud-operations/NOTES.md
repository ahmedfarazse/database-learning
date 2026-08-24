# CRUD Operations

## Introduction

**CRUD** is an acronym that stands for **C**reate, **R**ead, **U**pdate, and **D**elete. These are the four basic functions required to manage data. In SQL, specific commands correspond to each of these operations.

---

## 1. Create (INSERT)

To add new rows (records) into a table, we use the `INSERT INTO` statement.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2) 
VALUES (value1, value2);
```

**Example:**
```sql
INSERT INTO students (name, age, city) 
VALUES ('Ahmed', 22, 'Okara');
```

---

## 2. Read (SELECT)

To retrieve and view data from a database, we use the `SELECT` statement. This is the most frequently used SQL command.

**Syntax:**
```sql
SELECT column1, column2 FROM table_name;
```

**Example:**
```sql
-- To get specific columns
SELECT name, age FROM students;

-- To get all columns (using the asterisk *)
SELECT * FROM students;
```

---

## 3. Update (UPDATE)

To modify existing records in a table, we use the `UPDATE` statement. 

> **⚠️ WARNING:** Always use a `WHERE` clause with `UPDATE`. If you omit the `WHERE` clause, ALL records in the table will be updated!

**Syntax:**
```sql
UPDATE table_name 
SET column1 = value1, column2 = value2 
WHERE condition;
```

**Example:**
```sql
UPDATE students 
SET city = 'Lahore', age = 23 
WHERE name = 'Ahmed';
```

---

## 4. Delete (DELETE)

To remove existing records from a table, we use the `DELETE` statement.

> **⚠️ WARNING:** Just like UPDATE, always use a `WHERE` clause with `DELETE`. If you omit it, ALL records will be deleted!

**Syntax:**
```sql
DELETE FROM table_name WHERE condition;
```

**Example:**
```sql
DELETE FROM students WHERE name = 'Ali';
```

---

## Interview Questions

* What does CRUD stand for?
* Which SQL statement is used to retrieve data from a database?
* What happens if you run an `UPDATE` or `DELETE` statement without a `WHERE` clause?
* How do you insert multiple rows in a single `INSERT` statement?

---

## Quick Revision

* **C**reate → `INSERT INTO` (Adds new data)
* **R**ead → `SELECT` (Fetches data)
* **U**pdate → `UPDATE` (Modifies existing data)
* **D**elete → `DELETE` (Removes data)