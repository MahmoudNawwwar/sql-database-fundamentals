# DBMS vs RDBMS  
> Consolidated notes adapted from Mohammed Abu-Hadhoud’s “DBMS vs RDBMS” slide deck (2023). :contentReference[oaicite:0]{index=0}  

---

## 1 · Quick Definitions  

| Term | Essence |
|------|---------|
| **DBMS** – Database Management System | General-purpose software that stores and manages data—often in flat files or proprietary structures—**without enforced relations**. |
| **RDBMS** – Relational DBMS | Enhanced DBMS that stores data **in related tables** (rows & columns) and supports SQL, keys, and integrity constraints. |

---

## 2 · Comparison Matrix (Technical)  

| Feature | **DBMS** | **RDBMS** |
|---------|----------|-----------|
| **Data model** | Files, trees, XML – no mandatory relations | Tabular (tables) + defined relationships |
| **Query language** | Optional / proprietary | **SQL** standard |
| **Users / concurrency** | Single-user (typical) | Multi-user with locking, ACID txns |
| **Integrity constraints** | Minimal | `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `UNIQUE`, `NOT NULL` |
| **Normalization** | Not required → redundancy | Supports 1NF-3NF → strong integrity |
| **Typical products** | File system, XML store | MySQL, Oracle, SQL Server, PostgreSQL |
| **Data sharing** | Limited / local | Centralized, network-accessible |
| **Ease of use** | Custom code, harder joins | Standardized tooling & joins |

---

## 3 · Practical Differences (from the slides)  

| Aspect | **DBMS** | **RDBMS** |
|--------|----------|-----------|
| **Scalability & backup** | Small data, less scalable, backup is hard | Large data, more scalable, easy backup |
| **Security** | Basic / OS-level | Granular privileges, roles, encryption |
| **Redundancy** | No normalization → more redundancy | Normalization → less redundancy |
| **Data consistency** | Weak | Strong |
| **Data sharing** | Limited | Centralized, easy |
| **Learning curve** | Harder to work with | Easier (SQL + tools) |

---

## 4 · Visual Example (from the PDF)  

### 4.1 DBMS-style flat file  

