# Database Normalization

## Introduction

**Normalization** is the process of organizing data in a database to reduce redundancy (unnecessary duplication) and improve data integrity. 

When a database is properly normalized, each piece of data is stored in exactly one place.

---

## The Problem with Unnormalized Data

If you store all information in one giant table, you will face "Anomalies" (errors):
1. **Update Anomaly:** If a teacher's phone number changes, you might have to update it in 50 different student records. If you miss even one, your data becomes inconsistent.
2. **Deletion Anomaly:** If you delete the last student enrolled in a specific course, you might accidentally delete the entire course's details from the database.
3. **Wasted Space:** Repeating the same text (like a long department name or address) millions of times wastes storage.

---

## The Normal Forms

Database optimization is divided into stages called "Normal Forms". In practical software engineering, we usually normalize up to the **Third Normal Form (3NF)**.

### 1. First Normal Form (1NF)
**Rule: Each cell must contain a single (atomic) value.**
* **Bad:** A `skills` column containing `"Java, Python, SQL"`.
* **Good:** Each skill gets its own row, or a separate related table is created.

### 2. Second & Third Normal Form (2NF & 3NF)
**Rule: Every table should serve a single purpose (Entity), and all non key columns must depend entirely on the Primary Key.**
* **Meaning in Simple Terms:** Don't mix different types of data. A `Students` table should only contain student details. It should not contain the `Department_Head_Name`. 
* **The Fix:** Move the department details to a `Departments` table, and link them using a **Foreign Key**.

---

## Interview Questions

* What is Database Normalization and why is it important?
* What are Update, Insert, and Delete anomalies?
* What is the First Normal Form (1NF)?
* If a table has repeating customer addresses for every order, which database principle is it violating?

---

## Quick Revision

* **Normalization** → Organizing data to reduce duplication.
* **1NF** → Atomic values only (No comma separated lists).
* **2NF / 3NF** → Separate unrelated data into different tables and use Foreign Keys.