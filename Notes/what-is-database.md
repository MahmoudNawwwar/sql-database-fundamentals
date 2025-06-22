# What is a Database?  
> _Revision notes extracted from Mohammed Abu-Hadhoud’s “What is Database?” presentation (2023)._   
---

## 1. Definition

A **database** is an *organized collection of data* that can be accessed, managed, and updated efficiently. To handle databases we rely on **Database Management Systems (DBMS)**. :contentReference[oaicite:0]{index=0}

---

## 2. Types of DBMS

| Category | Description | Typical Examples |
|----------|-------------|------------------|
| **Non-Relational (DBMS)** | Data is stored without enforced relations; often file-based or semi-structured. | File System, XML, JSON stores |
| **Relational (RDBMS)** | Enhanced DBMS that stores data in related tables using keys and constraints. | SQL Server, Oracle, MySQL | :contentReference[oaicite:1]{index=1} |

---

## 3. Relational Model Building Blocks

| Term            | Synonyms              | Meaning                                   |
|-----------------|-----------------------|-------------------------------------------|
| **Table**       | *Entity-Set*          | Collection of related rows                |
| **Row**         | *Record, Entity*      | Single instance of data                   |
| **Column**      | *Field, Attribute*    | A property describing each row            | :contentReference[oaicite:2]{index=2} |

---

## 4. Example Schema

### 4.1 `Departments` Table

| `ID` | `Name`     | `Location` |
|------|------------|-----------|
| 1    | IT         | Amman     |
| 2    | Finance    | Amman     |
| 3    | HR         | UAE       |
| 4    | Marketing  | Qatar     | :contentReference[oaicite:3]{index=3} |

### 4.2 `Employees` Table

| `ID` | `FirstName` | `LastName`  | `Gender` | `Birthdate` | `Salary` | `DepartmentID` |
|------|-------------|-------------|----------|-------------|----------|----------------|
| 1    | Mohammed    | Abu-Hadhoud | M        | 1977-06-11  | 5000     | 1 |
| 2    | Ali         | Zaher       | M        | 1990-05-07  | 3000     | 2 |
| 3    | Lubna       | Aqel        | F        | 2000-05-05  |  500     | 1 |
| 5    | Fadi        | Khalil      | M        | 1980-06-06  | 1400     | 4 |
| 6    | Maha        | Majed       | M        | 2001-07-07  |  300     | 3 |
| 7    | Omar        | Ali         | M        | 1977-06-06  | 2000     | 1 |
| 8    | Huda        | Omar        | F        | 1990-04-02  | 1000     | 1 | :contentReference[oaicite:4]{index=4} |

---

## 5. Sample SQL

```sql
-- Create schema
CREATE TABLE Departments (
    ID           INT PRIMARY KEY,
    Name         VARCHAR(50) NOT NULL,
    Location     VARCHAR(50)
);

CREATE TABLE Employees (
    ID           INT PRIMARY KEY,
    FirstName    VARCHAR(50),
    LastName     VARCHAR(50),
    Gender       CHAR(1),
    Birthdate    DATE,
    Salary       DECIMAL(10,2),
    DepartmentID INT,
    CONSTRAINT FK_Dept
        FOREIGN KEY (DepartmentID) REFERENCES Departments(ID)
);
