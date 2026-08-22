# Database Fundamentals

## Introduction

A database is an organized way to store and manage data.

Databases are commonly used in applications to store information such as users, students, products, orders, courses, and transactions.

---

## What is a Database?

A database is an organized collection of data that can be stored, managed, and accessed when needed.

### Example

A Student Management System may store:

```text
Student Name
Student Age
Student Courses
Student Enrollment
```

Instead of keeping this data only inside the application memory, a database provides a structured and persistent way to manage it.

---

## What is a DBMS?

DBMS stands for **Database Management System**.

A DBMS is software used to create, store, manage, and access databases.

### Examples

* PostgreSQL
* MySQL
* SQLite
* Microsoft SQL Server
* Oracle Database

### Database vs DBMS

* **Database** → organized collection of data
* **DBMS** → software used to manage the database

---

## What is SQL?

SQL stands for **Structured Query Language**.

SQL is a language used to communicate with relational databases.

It can be used to:

* Create database structures
* Insert data
* Read data
* Update data
* Delete data

### Example

```sql
SELECT * FROM students;
```

This query retrieves data from the `students` table.

---

## What is PostgreSQL?

PostgreSQL is a **relational Database Management System (DBMS)**.

It uses SQL to work with relational databases.

### Important Difference

```text
SQL
↓
Language

PostgreSQL
↓
DBMS
```

SQL and PostgreSQL are not the same thing.

---

## Relational Databases

A relational database organizes data into **tables** and allows relationships between those tables.

### Example

```text
Student Management Database
        |
        ├── students
        ├── courses
        └── enrollments
```

The tables can be connected through relationships.

---

## Tables

A table stores related data in rows and columns.

### Example

```text
students

id | name  | age
---|-------|----
1  | Ahmed | 22
2  | Ali   | 21
3  | Usman | 23
```

Here:

* `students` → table
* `id`, `name`, `age` → columns
* Each student record → row

---

## Columns

A column represents a specific type of information stored in a table.

Example:

```text
id
name
age
```

In the `students` table:

* `id` → student identifier
* `name` → student name
* `age` → student age

---

## Rows

A row represents one complete record in a table.

Example:

```text
1 | Ahmed | 22
```

This represents one student's record.

### Important

Column headings are not counted as rows.

For example:

```text
id | name  | age    ← column headings
---|-------|----
1  | Ahmed | 22     ← row
2  | Ali   | 21     ← row
```

There are **2 rows**, not 3.

---

## Primary Key

A **Primary Key** uniquely identifies each row in a table.

Example:

```text
students

id | name  | age
---|-------|----
1  | Ahmed | 22
2  | Ali   | 21
3  | Usman | 23
```

Here, `id` can be the Primary Key.

### Example

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```

### Properties of a Primary Key

A Primary Key:

* Uniquely identifies a record.
* Must contain unique values.
* Cannot contain `NULL`.
* Is used to identify a specific row.

---

## Foreign Key

A **Foreign Key** is used to reference a record in another table.

It helps establish a relationship between tables.

### Example

Students:

```text
id | name
---|------
1  | Ahmed
2  | Ali
```

Courses:

```text
id | name
---|------------------
1  | Database Systems
2  | DSA
```

An `enrollments` table can connect them:

```text
student_id | course_id
-----------|----------
1          | 1
1          | 2
2          | 1
```

Here:

```text
student_id → students.id
course_id  → courses.id
```

These are references to records in other tables.

---

## Primary Key vs Foreign Key

| Primary Key               | Foreign Key                           |
| ------------------------- | ------------------------------------- |
| Uniquely identifies a row | References a row in another table     |
| Values must be unique     | Values can be repeated                |
| Cannot be `NULL`          | Can be `NULL` depending on the design |
| Identifies records        | Helps establish relationships         |

---

## Relationships

Relationships connect related data stored in different tables.

Example:

```text
students
    |
    ↓
enrollments
    ↑
    |
courses
```

The `enrollments` table connects students with courses.

For example:

```text
Ahmed → Database Systems
Ahmed → DSA
Ali   → Database Systems
```

---

## Many-to-Many Relationship

A student can take multiple courses.

A course can also have multiple students.

Therefore:

```text
Student ←→ Course
```

is a **many-to-many relationship**.

A separate `enrollments` table can be used to represent this relationship.

Example:

```text
enrollments

student_id | course_id
-----------|----------
1          | 1
1          | 2
2          | 1
```

---

## Common Mistakes

### 1. SQL and PostgreSQL are the same

Incorrect:

```text
SQL = PostgreSQL
```

Correct:

```text
SQL = Language
PostgreSQL = DBMS
```

---

### 2. Counting column headings as rows

Incorrect:

```text
id | name | age
1  | Ahmed | 22
2  | Ali   | 21
```

This has 3 rows.

Correct:

It has **2 data rows**.

---

### 3. Confusing Primary Key and Foreign Key

Primary Key:

```text
Uniquely identifies a record.
```

Foreign Key:

```text
References a record in another table.
```

---

### 4. Storing many values in unrelated columns

For example:

```text
student_id | course1 | course2 | course3
```

This becomes difficult to manage when the number of courses changes.

A relational design can instead use an `enrollments` table to represent the relationship.

---

## Interview Questions

* What is a database?
* What is a DBMS?
* What is the difference between a database and a DBMS?
* What is SQL?
* What is PostgreSQL?
* What is the difference between SQL and PostgreSQL?
* What is a relational database?
* What is a table?
* What is a row?
* What is a column?
* What is a Primary Key?
* What is a Foreign Key?
* What is the difference between a Primary Key and a Foreign Key?
* What is a relationship between tables?
* What is a many-to-many relationship?
* Why do we use an `enrollments` table?

---

## Quick Revision

```text
Database
→ Organized collection of data

DBMS
→ Software used to manage databases

SQL
→ Language used to communicate with relational databases

PostgreSQL
→ Relational DBMS

Table
→ Stores data in rows and columns

Column
→ Represents a type of information

Row
→ Represents one record

Primary Key
→ Uniquely identifies a row

Foreign Key
→ References a record in another table

Relationship
→ Connects related data between tables

Many-to-Many
→ One record can relate to many records on both sides
```
