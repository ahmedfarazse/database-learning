# Database Relationships

## Introduction

In a relational database, tables don't exist in isolation. They are connected to each other to form a complete picture of the data. These connections are called **Relationships**, and they are built using Primary Keys (PK) and Foreign Keys (FK).

There are three main types of relationships:

---

## 1. One-to-One (1:1)

In a 1:1 relationship, one record in Table A is linked to exactly one record in Table B.

*   **When to use:** Mainly used to split a very wide table into smaller logical pieces, or for security reasons (e.g., separating public user data from private details).
*   **Real-world Example:** A Citizen and a CNIC (ID Card). One citizen has one CNIC, and one CNIC belongs to one citizen.

### Example:
~~~text
users Table                 user_details Table
id (PK) | username      ->  user_id (FK/PK) | cnic_number
--------|---------          ----------------|------------
1       | ali123        ->  1               | 35201...
2       | ahmed99       ->  2               | 34101...
~~~

---

## 2. One-to-Many (1:N)

This is the most common relationship in databases. One record in Table A can be linked to multiple records in Table B.

*   **When to use:** When a single entity naturally contains or owns multiple sub-entities.
*   **Real-world Example:** A Department and Students. One department can have hundreds of students, but each student belongs to only one department.

### Example:
~~~text
departments (1)             students (N)
dept_id (PK) | name     <-  id (PK) | name  | dept_id (FK)
-------------|-----         --------|-------|-------------
101          | CS       <-  1       | Ali   | 101
                        <-  2       | Usman | 101
~~~

---

## 3. Many-to-Many (M:N)

In an M:N relationship, multiple records in Table A are linked to multiple records in Table B.

*   **Important Rule:** Relational databases *cannot* implement a Many-to-Many relationship directly. 
*   **The Solution:** We must create a third table called a **Junction Table** (or Pivot Table) to break the M:N into two 1:N relationships.
*   **Real-world Example:** Students and Courses. One student takes many courses, and one course has many students.

### Example (Using a Junction Table):

**1. students (Table A)**
~~~text
student_id (PK) | name
----------------|-------
1               | Ali
2               | Ahmed
~~~

**2. courses (Table B)**
~~~text
course_id (PK) | title
---------------|------
10             | Math
20             | Science
~~~

**3. student_courses (Junction Table)**
~~~text
student_id (FK) | course_id (FK)
----------------|---------------
1               | 10   (Ali takes Math)
1               | 20   (Ali takes Science)
2               | 10   (Ahmed takes Math)
~~~
*The Junction table holds the Foreign Keys from both parent tables.*

---

## Interview Questions

* What are the three types of relationships in a database?
* Give an example of a One-to-Many relationship.
* How do you implement a Many-to-Many relationship in SQL?
* What is a Junction Table (or Pivot Table) and why is it needed?
* In a One-to-Many relationship, which table gets the Foreign Key? (Answer: The "Many" table / Child table).

---

## Quick Revision

*   **1:1** → One record links to one record (e.g., User & Passport).
*   **1:N** → One record links to many records (e.g., Department & Employees). Most common.
*   **M:N** → Many records link to many records (e.g., Students & Courses). Requires a Junction Table.