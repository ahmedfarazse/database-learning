# SQL JOINs

## Introduction

A **JOIN** clause is used to combine rows from two or more tables, based on a related column between them (usually Primary and Foreign Keys).

---

## Types of JOINs

### 1. INNER JOIN
Returns records that have matching values in **both** tables.

* **Use Case:** Find only those students who have enrolled in a course.

**Syntax:**

    SELECT students.name, courses.course_name
    FROM students
    INNER JOIN courses ON students.course_id = courses.id;

---

### 2. LEFT JOIN (or LEFT OUTER JOIN)
Returns **all** records from the left table (Table 1), and the matched records from the right table (Table 2). The result is NULL from the right side if there is no match.

* **Use Case:** Get a list of all customers and their orders (even if a customer hasn't placed any order yet).

**Syntax:**

    SELECT customers.name, orders.order_date
    FROM customers
    LEFT JOIN orders ON customers.id = orders.customer_id;

---

### 3. RIGHT JOIN (or RIGHT OUTER JOIN)
Returns **all** records from the right table (Table 2), and the matched records from the left table (Table 1). The result is NULL from the left side when there is no match.

* **Use Case:** Get a list of all departments and the employees in them (even if a department currently has no employees).

**Syntax:**

    SELECT employees.name, departments.dept_name
    FROM employees
    RIGHT JOIN departments ON employees.dept_id = departments.id;

---

### 4. FULL JOIN (or FULL OUTER JOIN)
Returns all records when there is a match in **either** left or right table. It combines the results of both LEFT and RIGHT joins.

* **Use Case:** Show all students and all courses. If a student has no course, show NULL for the course. If a course has no students, show NULL for the student.

**Syntax:**

    SELECT students.name, courses.course_name
    FROM students
    FULL OUTER JOIN courses ON students.course_id = courses.id;

---

## Visualizing JOINs (Venn Diagrams)

* **INNER JOIN:** The overlapping middle part of two circles.
* **LEFT JOIN:** The entire left circle, including the overlap.
* **RIGHT JOIN:** The entire right circle, including the overlap.
* **FULL JOIN:** Both circles entirely.

---

## Interview Questions

* What is a JOIN in SQL and why is it needed?
* What is the difference between an `INNER JOIN` and a `LEFT JOIN`?
* Can you join more than two tables in a single SQL query? (Answer: Yes, you can chain multiple JOINs together).
* What will happen if you use a `LEFT JOIN` but there are no matching records in the right table?

---

## Quick Revision

* **INNER:** Only matching data.
* **LEFT:** All data from the Left table + matching data from Right.
* **RIGHT:** All data from the Right table + matching data from Left.
* **FULL:** All data from both tables (matches + non-matches).