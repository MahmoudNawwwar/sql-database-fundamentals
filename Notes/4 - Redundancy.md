# Data Redundancy & Normalization  
> Revision notes extracted from Mohammed Abu-Hadhoud’s **“Redundancy”** presentation (2023).  
> These notes are intended for second-pass revision, not first-time study. :contentReference[oaicite:0]{index=0}  

---

## 1 · What Is Data Redundancy?

* **Data redundancy** is the existence of duplicate or derivable information inside a data store.  
  * Same facts stored in multiple locations.  
  * Values that could be calculated or referenced instead of stored. :contentReference[oaicite:1]{index=1}  

---

## 2 · Why Is Redundancy a Problem?

| Impact | Description |
|--------|-------------|
| **Wasted storage** | Every duplicate copy consumes extra disk space. |
| **Inconsistency** | One copy updated, another forgotten → conflicting values. |
| **Corruption risk** | Partial updates or manual fixes introduce errors. |
| **Integrity issues** | Violates single-source-of-truth; queries return unreliable results. |
| **Maintenance effort** | More columns/files to inspect, back-up, and migrate. :contentReference[oaicite:2]{index=2} |

---

## 3 · Illustrative Example

### 3.1 Flat-file (redundant) employee list  

| EmpID | FirstName | LastName | DeptID | DeptName | DeptLocation |
|-------|-----------|----------|--------|----------|--------------|
| 1 | Mohammed | Abu-Hadhoud | **1** | **IT** | **Amman** |
| 2 | Ali      | Zaher       | **1** | **IT** | **Amman** |
| 3 | Lubna    | Aqel        | **1** | **IT** | **Amman** |

*`DeptName` and `DeptLocation` repeat for every employee in the same department—classic redundancy.* :contentReference[oaicite:3]{index=3}  

### 3.2 Normalized alternative  

| **Departments** |            |            |
|-----------------|------------|------------|
| DeptID (PK)     | DeptName   | Location   |

| **Employees** |            |            |          |
|---------------|------------|------------|----------|
| EmpID (PK)    | FirstName  | LastName   | DeptID → Departments(DeptID) |

Now department attributes live **once**, referenced by a foreign key—redundancy eliminated.

---

## 4 · Normalization in a Nutshell

* **Normalization** is the systematic process of restructuring tables to **minimize redundancy** and **maximize integrity**.  
* Achieved through *normal forms* (1NF → 5NF). Key themes:  
  1. Break repeating groups into separate tables.  
  2. Store each fact exactly once.  
  3. Link tables with **primary / foreign keys**. :contentReference[oaicite:4]{index=4}  

```sql
-- 1NF / 2NF style split
CREATE TABLE Departments (
    DeptID      INT PRIMARY KEY,
    DeptName    VARCHAR(50) NOT NULL,
    Location    VARCHAR(50)
);

CREATE TABLE Employees (
    EmpID       INT PRIMARY KEY,
    FirstName   VARCHAR(50),
    LastName    VARCHAR(50),
    DeptID      INT NOT NULL,
    FOREIGN KEY (DeptID) REFERENCES Departments(DeptID)
);
