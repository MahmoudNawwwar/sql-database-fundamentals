# Database Constraints  
> Revision notes extracted from Mohammed Abu-Hadhoud’s **“What is Constraint?”** presentation (2023).  
> These notes are intended for second-pass revision and assume basic SQL knowledge. :contentReference[oaicite:0]{index=0}  

---

## 1 · Definition  

* A **constraint** is a rule attached to a table or column that enforces **data integrity and consistency**.  
* Constraints prevent invalid, duplicate, or incomplete data from being stored, making the database trustworthy and easier to manage. :contentReference[oaicite:1]{index=1}  

---

## 2 · Why Constraints Matter  

| Benefit | How It Helps |
|---------|--------------|
| **Accuracy** | Blocks impossible or ill-formed values. |
| **Consistency** | Keeps related tables in sync (referential integrity). |
| **Uniqueness** | Prevents duplicate rows or values. |
| **Completeness** | Forces required columns to be filled. |
| **Maintainability** | Reduces manual clean-up and error handling. |

---

## 3 · Five Core Constraint Types  

| # | Constraint | Purpose | Key Rules | Typical Syntax |
|---|------------|---------|-----------|----------------|
| 1 | **Primary Key** | Uniquely identifies each row. | Must be **unique** and **NOT NULL**. One PK per table. | `PRIMARY KEY (id)` |
| 2 | **Foreign Key** | Links a child table to a parent table. | Value must exist in referenced PK; maintains referential integrity. | `FOREIGN KEY (dept_id) REFERENCES Departments(id)` |
| 3 | **Unique** | Ensures values in a column (or set) are unique. | Allows **NULL** (unless `NOT NULL` also applied). | `UNIQUE (email)` |
| 4 | **Not Null** | Disallows NULL values. | Column must always contain data. | `salary DECIMAL NOT NULL` |
| 5 | **Check** | Enforces a custom Boolean condition. | Rejects rows that violate expression. | `CHECK (salary >= 0)` | :contentReference[oaicite:2]{index=2}  

---

## 4 · Quick Reference Example  

```sql
CREATE TABLE Departments (
    id        INT PRIMARY KEY,
    name      VARCHAR(50) NOT NULL,
    location  VARCHAR(50)
);

CREATE TABLE Employees (
    id        INT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name  VARCHAR(50) NOT NULL,
    gender     CHAR(1) CHECK (gender IN ('M','F')),
    birthdate  DATE      CHECK (birthdate > '1900-01-01'),
    salary     DECIMAL(10,2) CHECK (salary >= 0),
    dept_id    INT  NOT NULL,
    CONSTRAINT fk_emp_dept
        FOREIGN KEY (dept_id) REFERENCES Departments(id)
        ON UPDATE CASCADE
        ON DELETE RESTRICT,
    CONSTRAINT uq_emp_fullname
        UNIQUE (first_name, last_name, birthdate)
);
