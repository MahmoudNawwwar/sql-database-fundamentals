## ERD Relationships  
> Adapted from Mohammed Abu-Hadhoud’s “Relationships” slide deck (2023). :contentReference[oaicite:0]{index=0}  

### 1 · What Is a Relationship?  
A **relationship** shows how two (or more) entities interact.  
In an ER diagram it is drawn as a **diamond** placed between entity rectangles.  


---

### 2 · Classic Examples from the Slides  

| Entities | Relationship | Comment |
|----------|--------------|---------|
| Student – Course | **Enrolled** | Typical many-to-many (M:N) |
| Student – Identification Card | **Has** | One-to-one (1:1) |
| Customer – Order | **Place** | One-to-many (1:M) |
| Order – Product | **Contains** | Order may contain many products |
| Member – Book | **Borrow** | Many-to-many via a borrowing table |
| Customer – Car | **Rent** | One customer may rent many cars |
| Employee – Project | **Works on**, **Manages** | Employee both works on and can manage projects |

---

### 3 · Self-Referencing Relationship  
A relationship where **an entity relates to itself**.  
Example: an employee manages other employees.


| ID | Name  | Salary | ManagerID |
|----|-------|--------|-----------|
| 1  | Ahmed | 5000   | NULL |
| 2  | Amjad | 1500   | 1 |
| 3  | Maher | 1300   | 2 |
| 4  | Alia  | 500    | 2 |

*`ManagerID` is a **foreign key** pointing back to `Employee.ID`.*  

---

### 4 · Relationship Cardinalities  

| Type | Diagram Notation | Real-world Example |
|------|------------------|--------------------|
| **One-to-One (1:1)** | Single line both sides | Person ↔ Passport |
| **One-to-Many (1:M)** | Single line → crow-feet | Department → Employee |
| **Many-to-One (M:1)** | Crow-feet → single line | Employee → Department |
| **Many-to-Many (M:N)** | Crow-feet both sides | Student ↔ Course |

---

### 5 · Why Relationships Matter  

1. **Logical clarity** – show how data objects depend on one another.  
2. **Referential integrity** – foreign keys in SQL mirror the ER relationships.  
3. **Query design** – understanding cardinality guides join strategy and indexing.  
4. **Business rules** – relationships document real-world constraints (e.g., one ID card per student).

---

