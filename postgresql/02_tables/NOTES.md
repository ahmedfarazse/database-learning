# Database Tables

## Introduction

A table is one of the core components of a relational database.

Tables store related data in rows and columns.

---

## What is a Table?

A table stores a specific type of related data in an organized structure.

Example:

```text
students

id | name  | age
---|-------|----
1  | Ahmed | 22
2  | Ali   | 21
3  | Usman | 23
```

Here:

- `students` → table
- `id`, `name`, `age` → columns
- Each student record → row

---

## Columns

A column represents a specific type of information stored in a table.

Example:

```text
id
name
age
city
```

For a `students` table:

- `id` → student identifier
- `name` → student name
- `age` → student age
- `city` → student's city

---

## Rows

A row represents one complete record in a table.

Example:

```text
1 | Ahmed | 22 | Okara
```

This represents one student's complete record.

---

## Table Structure

A simple way to understand a table:

```text
Table
│
├── Columns → types/categories of data
│
└── Rows → actual records
```

Example:

```text
students

id | name  | age
---|-------|----
1  | Ahmed | 22
2  | Ali   | 21
```

There are:

- 3 columns
- 2 data rows

The column headings are not counted as rows.

---

## Multiple Tables

A database can contain multiple tables.

For example, a university database may contain:

```text
University Database
│
├── students
├── courses
└── teachers
```

Each table stores a different type of related data.

### Students

```text
id | name  | age
---|-------|----
1  | Ahmed | 22
2  | Ali   | 21
```

### Courses

```text
id | name
---|------------------
1  | Database Systems
2  | DSA
```

### Teachers

```text
id | name
---|-----------
1  | Dr. Ahmed
2  | Dr. Ali
```

Separating different types of data into different tables keeps the database organized and easier to manage.

---

## Creating a Table

In SQL, the `CREATE TABLE` statement is used to create a table.

Example:

```sql
CREATE TABLE students (
    id INT,
    name VARCHAR(100),
    age INT
);
```

This creates a table named `students` with three columns:

```text
id
name
age
```

---

## Common Mistakes

### 1. Confusing a Database with a Table

A database can contain multiple tables.

```text
Database
│
├── students
├── courses
└── teachers
```

A table is a structure inside the database.

---

### 2. Counting Column Headings as Rows

```text
id | name  | age
---|-------|----
1  | Ahmed | 22
2  | Ali   | 21
```

This table has:

- 3 columns
- 2 rows

The header is not a data row.

---

### 3. Putting Unrelated Data in One Table

Instead of putting everything into one large table:

```text
students + courses + teachers
```

different types of data can be stored in separate tables.

This makes the database easier to manage and allows relationships to be created between tables.

---

## Interview Questions

- What is a database table?
- What is the difference between a database and a table?
- What is a row?
- What is a column?
- Why do relational databases use tables?
- Why do we use multiple tables in a database?
- Which SQL statement is used to create a table?
- What does `CREATE TABLE` do?

---

## Quick Revision

- Table → stores related data
- Column → represents a type of information
- Row → represents one complete record
- Database → can contain multiple tables
- `CREATE TABLE` → SQL statement used to create a table