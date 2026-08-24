# Database Constraints

## Introduction

**Constraints** are rules applied to data columns in a database table. They are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data. If any operation violates a constraint, the database will throw an error and abort the action.

---

## The 6 Main SQL Constraints

### 1. NOT NULL
Ensures that a column cannot have a NULL (empty) value.
* **Example:** A user creating an account *must* provide a password.

### 2. UNIQUE
Ensures that all values in a column are different. No duplicates are allowed.
* **Example:** Usernames or Email addresses must be unique across the platform.

### 3. PRIMARY KEY
A combination of a `NOT NULL` and `UNIQUE` constraint. It uniquely identifies each row in a table.

### 4. FOREIGN KEY
Prevents actions that would destroy links between tables. It ensures that the value in one table must match an existing primary key in another table.

### 5. CHECK
Ensures that the values in a column satisfy a specific condition.
* **Example:** Ensuring an item's price is always greater than 0, or a voter's age is 18+.

### 6. DEFAULT
Sets a default value for a column if no value is specified during an `INSERT` operation.
* **Example:** Setting a user's account status to 'Active' by default.

---

## Syntax Example (Creating a Table with Constraints)

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,                       -- Must be unique and not null
    username VARCHAR(50) UNIQUE NOT NULL,     -- No duplicates, cannot be empty
    age INT CHECK (age >= 18),                -- Value must be 18 or older
    status VARCHAR(20) DEFAULT 'active'       -- Will be 'active' if left blank
);
```

---

## Interview Questions

* What is the purpose of database constraints?
* What is the difference between a `UNIQUE` constraint and a `PRIMARY KEY`?
* Can a table have multiple `UNIQUE` constraints? (Answer: Yes).
* If you want to automatically set the signup date to the current date when a user registers, which constraint would you use? (Answer: `DEFAULT`).

---

## Quick Revision

* **NOT NULL** → No empty values.
* **UNIQUE** → No duplicate values.
* **PRIMARY KEY** → Unique identifier (NOT NULL + UNIQUE).
* **FOREIGN KEY** → Links to another table's Primary Key.
* **CHECK** → Validates a logical condition.
* **DEFAULT** → Fills in a default value if none is provided.