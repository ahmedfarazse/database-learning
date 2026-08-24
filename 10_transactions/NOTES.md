# Database Transactions

## Introduction

A **Transaction** is a sequence of multiple SQL operations treated as a single logical unit of work. The fundamental rule of a transaction is: **Either all operations succeed, or none of them do.** There is no halfway point.

This is critical in real world applications like banking, e-commerce, and ticketing systems where data accuracy is non negotiable.

---

## Transaction Commands

1. **BEGIN (or START TRANSACTION):** Marks the beginning of a transaction block.
2. **COMMIT:** Saves all the changes made during the transaction permanently to the database. Used when everything runs successfully.
3. **ROLLBACK:** Cancels the transaction and undoes all changes made since `BEGIN`. Used when an error occurs.

### Real-World Example (Bank Transfer)

Transferring $500 from Account A to Account B:

    BEGIN;

    -- Step 1: Deduct from Account A
    UPDATE accounts SET balance = balance - 500 WHERE account_id = 'A';

    -- Step 2: Add to Account B
    UPDATE accounts SET balance = balance + 500 WHERE account_id = 'B';

    -- If both steps succeed without error:
    COMMIT; 

    -- If any step fails (e.g., system crash, server error):
    -- ROLLBACK; (This will cancel Step 1 as well)

---

## ACID Properties

To guarantee validity even in the event of errors, power failures, or crashes, database transactions must follow the **ACID** principles:

* **A - Atomicity:** "All or Nothing." The transaction is treated as a single, indivisible unit. If one part fails, the entire transaction fails.
* **C - Consistency:** The database must transition from one valid state to another. All constraints and rules must be followed.
* **I - Isolation:** Multiple transactions running concurrently (at the same time) must not interfere with each other. (e.g., Two people trying to book the same movie seat).
* **D - Durability:** Once a transaction has been committed, the changes are permanent and will survive system failures or power outages.

---

## Interview Questions

* What is a database transaction?
* Explain the ACID properties with an example.
* When would you use a `ROLLBACK` instead of a `COMMIT`?
* What happens if a server crashes in the middle of a transaction before the `COMMIT` command is executed?

---

## Quick Revision

* **BEGIN** → Start the process.
* **COMMIT** → Save the process permanently.
* **ROLLBACK** → Abort and undo the process.
* **ACID** → Atomicity, Consistency, Isolation, Durability.