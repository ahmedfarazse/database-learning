# Database Indexes

## Introduction

An **Index** is a database structure that improves the speed of data retrieval (Read operations) on a table at the cost of additional storage space and slower writes (Insert, Update, Delete).

Think of it like the index at the back of a large textbook. Instead of flipping through thousands of pages to find a specific word (a Full Table Scan), you look at the index to find the exact page number.

---

## Creating and Dropping Indexes

**1. CREATE INDEX**
Creates an index on a table. Duplicate values are allowed.

**Syntax:**

    CREATE INDEX index_name
    ON table_name (column1, column2, ...);


**Example:**

    -- Speed up searches for users by their email
    CREATE INDEX idx_user_email 
    ON users (email);


**2. CREATE UNIQUE INDEX**
Creates an index where duplicate values are not allowed (often automatically created for Primary Keys).

**Example:**

    CREATE UNIQUE INDEX idx_cnic 
    ON citizens (cnic_number);


**3. DROP INDEX**
Deletes an index if it is no longer needed or is slowing down insertions.

**Example:**

    DROP INDEX idx_user_email ON users;

---

## The Trade-Offs (Pros & Cons)

### ✅ Pros:
* Dramatically speeds up `SELECT` queries, especially those with `WHERE`, `ORDER BY`, or `JOIN` clauses.

### ❌ Cons:
* Takes up extra disk space (memory).
* Slows down `INSERT`, `UPDATE`, and `DELETE` operations because the index must also be updated every time the table data changes.

---

## When to Use Indexes?
* On columns that are frequently used in the `WHERE` clause (e.g., search queries).
* On Foreign Key columns to speed up `JOIN` operations.
* On tables that have a huge number of records and are mostly used for reading data rather than writing.

## When NOT to Use Indexes?
* On small tables (scanning a small table is already fast).
* On tables that have frequent, large batch updates or inserts (like logging systems).
* On columns that contain a high number of NULL values or boolean values (e.g., `is_active` True/False), because the index won't be very efficient.

---

## Interview Questions

* What is a database index and how does it work?
* Why shouldn't you index every single column in a table?
* What happens to `INSERT` and `UPDATE` speeds when you add an index?
* What is the difference between a Clustered and a Non Clustered index? (Advanced)

---

## Quick Revision

* **Index** → Speeds up reads (`SELECT`), slows down writes (`INSERT`/`UPDATE`/`DELETE`).
* **Table Scan** → Searching row by row (Very slow for large tables).
* Always balance the need for fast searches against the cost of storage and write performance.