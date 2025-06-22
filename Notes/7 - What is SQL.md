# What is SQL?  
> Revision notes extracted from Mohammed Abu-Hadhoud’s **“What is SQL?”** presentation (2023).  
> These notes are intended for second-pass revision and assume basic database concepts. :contentReference[oaicite:0]{index=0}  

---

## 1 · Definition  

* **SQL** stands for **Structured Query Language**.  
* Pronounced either **“S-Q-L”** or **“See-Quel.”**  
* Standard language used to **communicate with, access, and manipulate relational databases** across products such as Oracle, Sybase, Microsoft SQL Server, Access, and Ingres. :contentReference[oaicite:1]{index=1}  

---

## 2 · What Can You Do with SQL?  

| Capability | Example |
|------------|---------|
| Execute queries | `SELECT * FROM Employees;` |
| Retrieve data | `SELECT FirstName, LastName FROM Employees;` |
| Insert records | `INSERT INTO Employees VALUES (...);` |
| Update records | `UPDATE Employees SET Salary = 4000 WHERE ID = 7;` |
| Delete records | `DELETE FROM Employees WHERE ID = 7;` |
| Create databases | `CREATE DATABASE MyDB;` |
| Create tables | `CREATE TABLE Employees (...);` |
| Create views & procedures | `CREATE VIEW v_Employees AS …;` |
| Set permissions | `GRANT SELECT ON Employees TO Analyst;` | :contentReference[oaicite:2]{index=2}  

---

## 3 · Example SQL Statements  

```sql
-- Filtering rows
SELECT * 
FROM   Employees 
WHERE  Salary < 1000;

-- Combined conditions
SELECT FirstName, LastName
FROM   Employees
WHERE  Salary < 1000
  AND  Gender = 'M';

-- Range search
SELECT * 
FROM   Employees 
WHERE  Salary BETWEEN 500 AND 1000;

-- Aggregations
SELECT COUNT(*)      FROM Employees;
SELECT SUM(Salary)   FROM Employees;
SELECT AVG(Salary)   FROM Employees;

-- Data modification
DELETE FROM Employees WHERE ID = 10;
UPDATE Employees 
SET    FirstName = 'Amjad' 
WHERE  ID = 10;
``` :contentReference[oaicite:3]{index=3}  

---

## 4 · DDL, DML, DCL, TCL, DQL — The Five SQL Command Families  

| Family | Purpose | Typical Commands | Mnemonic |
|--------|---------|------------------|----------|
| **DDL**<br>Data Definition Language | Define or alter structures | `CREATE`, `DROP`, `ALTER`, `TRUNCATE` | *“Shape it”* |
| **DML**<br>Data Manipulation Language | Change data inside tables | `INSERT`, `UPDATE`, `DELETE` | *“Change it”* |
| **DCL**<br>Data Control Language | Control access/rights | `GRANT`, `REVOKE` | *“Guard it”* |
| **TCL**<br>Transaction Control Language | Manage transactions | `COMMIT`, `ROLLBACK`, `SAVEPOINT` | *“Group it”* |
| **DQL**<br>Data Query Language | Query data | `SELECT` | *“Get it”* | :contentReference[oaicite:4]{index=4}  

---

## 5 · Cheat-Sheet of Core Commands  

| Goal | Minimal Syntax |
|------|----------------|
| Create a database | `CREATE DATABASE db_name;` |
| Create a table | `CREATE TABLE tbl (...);` |
| Retrieve data | `SELECT columns FROM tbl WHERE …;` |
| Update a row | `UPDATE tbl SET col = val WHERE pk = …;` |
| Delete a row | `DELETE FROM tbl WHERE pk = …;` |
| Commit work | `COMMIT;` |
| Undo uncommitted work | `ROLLBACK;` |

---

## 6 · Summary  

* **SQL is the universal language for relational databases.**  
* It spans five families of commands covering **definition, manipulation, security, transaction, and querying**.  
* Mastering SQL foundations unlocks database creation, maintenance, and analysis across virtually every RDBMS. :contentReference[oaicite:5]{index=5}  

---

## 7 · License  

Original slide content © 2023 Mohammed Abu-Hadhoud / ProgrammingAdvices.com.  
This Markdown adaptation is released under the MIT License.
