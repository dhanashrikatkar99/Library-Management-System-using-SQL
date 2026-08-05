# Library-Management-System-using-SQL

```markdown
# Library Management System (SQL Project)

**A fully‑functional relational database for a library, implemented in PostgreSQL, with CRUD operations, advanced analytical queries, and automated stored procedures.**

---

## 📌 Project Overview

This project designs and implements a Library Management System database from scratch. It includes normalized tables for branches, employees, members, books, issued status, and return status. The analysis covers 20 SQL tasks ranging from basic CRUD to complex joins, aggregations, CTAS (Create Table As Select), subqueries, window functions, and stored procedures.

Key objectives:
- Model real‑world library operations (book issues/returns, member management, employee tracking).
- Generate actionable business reports (branch performance, revenue, overdue books, active members).
- Automate inventory status updates via stored procedures.
- Demonstrate advanced SQL problem‑solving skills.

---

## 🗃️ Database Schema

The ERD consists of six core tables:

| Table | Description |
|-------|-------------|
| `branch` | Library branches with manager and contact details |
| `employees` | Staff information, linked to branches |
| `members` | Library members and registration dates |
| `books` | Book inventory (ISBN, title, category, rental price, availability) |
| `issued_status` | Transaction log of every book issue |
| `return_status` | Transaction log of book returns |

**Primary/foreign key relationships** enforce data integrity.

---

## 🛠️ Tools & Technologies

- **PostgreSQL** – relational database management system
- **pgAdmin / psql** – administration and query execution
- **SQL** – all queries, views, and stored procedures

---

## 📊 Analysis Tasks & Insights

The following 20 tasks were executed. Key insights are highlighted.

### CRUD Operations (Tasks 1–5)
- Inserted a new book (`To Kill a Mockingbird`).
- Updated a member's address.
- Deleted an issued record.
- Retrieved all books issued by a specific employee.
- Found members with more than one issued book.

### CTAS (Task 6)
- Created `book_issued_cnt` – a summary table showing total issues per book, enabling identification of bestsellers.

### Data Analysis Queries (Tasks 7–12)
- **Books by category:** Filtered classics.
- **Rental income by category:** Classic books generate the highest total rental revenue.
- **New members (last 180 days):** A list for targeted engagement.
- **Employee‑branch‑manager hierarchy:** Joined employees with branches and managers.
- **Expensive books (> $7 rental price):** Isolated high‑value inventory.
- **Unreturned books:** Left join identified all books that are still out – critical for inventory tracking.

### Advanced SQL (Tasks 13–20)
- **Overdue books (30+ days):** Calculated days overdue for each member. Identified repeat offenders.
- **Stored procedure `add_return_records`:** Updates book status to 'yes' upon return, ensuring real‑time availability.
- **Branch performance report:** Created `branch_reports` with issue count, return count, and total revenue per branch. Uneven performance observed.
- **Active members (last 2 months):** CTAS to list members who recently borrowed.
- **Top 3 employees:** Ranked by number of issues processed – useful for performance evaluation.
- **High‑risk members (damaged books):** Identified members with multiple damaged book returns (flagged for enforcement).
- **Stored procedure `issue_book`:** Checks availability, issues book, and updates status to 'no' – prevents double‑booking.
- **Overdue fines CTAS:** Calculated total fines ($0.50/day) per member for overdue books – a potential revenue stream.


