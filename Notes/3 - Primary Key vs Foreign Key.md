# Primary Key vs Foreign Key  
> Revision notes extracted from Mohammed Abu-Hadhoud’s “**Primary Key vs Foreign Key**” presentation (2023).  
> These notes are for second-pass revision and assume basic SQL familiarity. :contentReference[oaicite:0]{index=0}  

---

## 1 · Relational Context

In an RDBMS, data are stored in *tables* (entity sets) composed of *rows* (records) and *columns* (attributes). Relationships between tables are expressed through keys. :contentReference[oaicite:1]{index=1}  

---

## 2 · Primary Key (PK)

* A **primary key** is a column—or a minimal set of columns—that **uniquely identifies every row** in a table.  
* Requirements:  
  * **Unique** for each record.  
  * **Non-NULL** at all times.  
  * **Stable**—should rarely, if ever, change.  
* Every table **must** have exactly one primary key. :contentReference[oaicite:2]{index=2}  

---

## 3 · Foreign Key (FK)

* A **foreign key** is a column—or set of columns—in one table that **references the primary key** of another table.  
* Purpose:  
  * Creates a **parent–child relationship** between tables.  
  * Enforces **referential integrity**: every FK value must exist in the referenced PK column.  
* Allows meaningful joins and prevents orphaned records. :contentReference[oaicite:3]{index=3}  

---

## 4 · Side-by-Side Comparison

| Feature                | Primary Key (PK)                          | Foreign Key (FK)                            |
|------------------------|-------------------------------------------|---------------------------------------------|
| **Uniqueness**         | Must be unique                            | May repeat values                           |
| **NULL Allowed?**      | Never NULL                                | May be NULL (if relationship is optional)   |
| **Table Ownership**    | Defined *inside* its own table            | Points to PK of another (parent) table      |
| **Referential Role**   | Source of truth for identity              | Enforces referential integrity              |
| **Indexing**           | Automatically indexed (in most RDBMS)     | Often indexed for performance, not mandatory|
| **Update Behavior**    | Rarely changed                            | Changes follow PK updates (CASCADE/RESTRICT)|

---

## 5 · Example Schema

```sql
CREATE TABLE Departments (
    ID        INT PRIMARY KEY,
    Name      VARCHAR(50) NOT NULL,
    Location  VARCHAR(50)
);

CREATE TABLE Employees (
    ID           INT PRIMARY KEY,
    FirstName    VARCHAR(50),
    LastName     VARCHAR(50),
    Gender       CHAR(1),
    Birthdate    DATE,
    Salary       DECIMAL(10,2),
    DepartmentID INT,
    CONSTRAINT FK_Employees_Departments
        FOREIGN KEY (DepartmentID)
        REFERENCES Departments(ID)
        ON UPDATE CASCADE
        ON DELETE RESTRICT
);
