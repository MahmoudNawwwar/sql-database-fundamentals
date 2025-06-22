# NULL in Relational Databases  
> Revision notes extracted from Mohammed Abu-Hadhoud’s “**What is NULL?**” presentation (2023).  
> These notes are intended for second-pass revision, not for first-time study. :contentReference[oaicite:0]{index=0}  

---

## 1 · Definition

* **NULL** is a special marker that indicates **“no value”** or **“unknown value”** in a column.  
* It is **not** equivalent to an empty string (`''`) or zero (`0`); those are actual, known values. :contentReference[oaicite:1]{index=1}  

---

## 2 · Why Does NULL Matter?

| Reason | Practical Impact |
|--------|------------------|
| Represents missing data | Keeps a slot for information that will arrive later. |
| Adds model flexibility | Optional columns do not require a default placeholder. |
| Affects query results | Aggregate functions (`SUM`, `AVG`) skip NULLs; comparisons with `=` or `<>` never match NULL rows. :contentReference[oaicite:2]{index=2} |

---

## 3 · NULL ≠ Empty String ≠ Zero

| Value | Meaning | Example |
|-------|---------|---------|
| `NULL` | Unknown or not applicable | Birthdate not provided |
| `''`   | Known, but intentionally left blank | A comment left empty |
| `0`    | Numeric value zero | Discount = 0 EGP | :contentReference[oaicite:3]{index=3} |

---

## 4 · Sample Data Containing NULL

### 4.1 `Employees`

| ID | FirstName | LastName    | Gender | Birthdate | Salary | DepartmentID |
|----|-----------|-------------|--------|-----------|--------|--------------|
| 1  | Mohammed  | Abu-Hadhoud | M      | 1977-06-11 | 5000   | 1 |
| 2  | Ali       | Zaher       | M      | **NULL**   | **NULL** | 2 |
| 3  | Lubna     | Aqel        | F      | 2000-05-05 |  500   | 1 |
| …  | …         | …           | …      | …         | …      | … | :contentReference[oaicite:4]{index=4} |

### 4.2 `Departments`

| ID | Name       | Location |
|----|------------|----------|
| 1  | IT         | Amman |
| 2  | Finance    | Amman |
| 3  | HR         | UAE |
| 4  | Marketing  | Qatar | :contentReference[oaicite:5]{index=5} |

---

## 5 · Working with NULL in SQL

```sql
-- 1) Find rows where a column is NULL
SELECT *
FROM   Employees
WHERE  Birthdate IS NULL;

-- 2) Replace NULL with a default value
SELECT FirstName,
       COALESCE(Salary, 0) AS Salary_LMT
FROM   Employees;

-- 3) Ensure aggregates ignore NULL automatically
SELECT DepartmentID,
       AVG(Salary) AS AvgSalary
FROM   Employees
GROUP  BY DepartmentID;   -- AVG skips rows where Salary IS NULL
