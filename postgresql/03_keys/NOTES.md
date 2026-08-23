# Database Keys

## Introduction

In a relational database, **Keys** are used to uniquely identify a row in a table and to establish relationships between different tables. The two most important types of keys are **Primary Keys** and **Foreign Keys**.

---

## Primary Key (PK)

A Primary Key is a column (or a set of columns) that uniquely identifies each row in a table.

**Rules for a Primary Key:**
1. **Unique:** No two rows can have the same primary key value.
2. **Not Null:** A primary key cannot be empty (NULL).
3. **One per table:** A table can only have one primary key.

### Example:

~~~text
students

id (PK) | name  | age
--------|-------|----
1       | Ahmed | 22
2       | Ali   | 21
3       | Usman | 23
~~~

*Here, `id` is the Primary Key. Even if two students are named "Ahmed", their `id` will always be different.*

---

## Foreign Key (FK)

A Foreign Key is a column in one table that refers to the Primary Key in another table. It acts as a bridge to connect the two tables.

**Rules for a Foreign Key:**
1. It must reference an existing Primary Key in another table.
2. It can contain duplicate values (many rows can refer to the same foreign record).
3. It can be NULL (if the relationship is optional).

### Example of Linking Tables:

Let's link `students` to their `departments`.

**1. departments Table (Parent)**

~~~text
dept_id (PK) | dept_name
-------------|------------------
101          | Computer Science
102          | Mathematics
~~~

**2. students Table (Child)**

~~~text
id (PK) | name  | dept_id (FK)
--------|-------|-------------
1       | Ahmed | 101
2       | Ali   | 101
3       | Usman | 102
~~~

*Here, `dept_id` in the `students` table is a Foreign Key that links directly to the `dept_id` Primary Key in the `departments` table.*

---

## Creating Keys in SQL

Here is how you define these keys when creating tables:

~~~sql
-- Creating the Parent Table First
CREATE TABLE departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(100)
);

-- Creating the Child Table Second
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);
~~~

---

## Interview Questions

* What is a Primary Key and what are its properties?
* What is the difference between a Primary Key and a Foreign Key?
* Can a table have multiple Primary Keys?
* Can a Foreign Key be NULL?
* What happens if you try to insert a Foreign Key value that doesn't exist in the parent table's Primary Key?

---

## Quick Revision

* **Primary Key (PK)** → Uniquely identifies a record (e.g., Student ID). Unique & Not Null.
* **Foreign Key (FK)** → Connects a table to another table (e.g., Department ID in Students table).
* **Parent Table** → The table holding the Primary Key.
* **Child Table** → The table holding the Foreign Key.