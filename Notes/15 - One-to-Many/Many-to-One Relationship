# One-to-Many / Many-to-One Relationship  
> Adapted from Mohammed Abu-Hadhoud’s “One-to-Many / Many-to-One Relationship” slide deck (2023).  

---

## 1 · Definition  

* **One-to-Many (1 : M)** – a single row in Entity A can be associated with **multiple** rows in Entity B.  
* **Many-to-One (M : 1)** – the inverse view: many rows in Entity B relate back to **one** row in Entity A.  

---

## 2 · Slide Examples  

| Relationship | Cardinality | Business Rule |
|--------------|-------------|---------------|
| **Customer** *places* **Order** | 1 : M | One customer can place many orders; an order belongs to one customer. |
| **Employee** *works on* **Project** | M : 1 | Many employees may work on one project; employee linked to a single project. |
| **Member** *borrows* **Book** | 1 : M | A member can borrow many books; each book is borrowed by one member at a time. |
| **Customer** *subscribes to* **Mobile Line** | 1 : M | One customer may own many lines; each line belongs to one customer. |
| **Citizen** *owns* **Car** | 1 : M | A citizen can own many cars; each car is owned by one citizen. |

---

### 2.1 Self-Relationship (Hierarchical)  

*An entity related to itself.*  
Example: an **Employee** has exactly one manager, but a manager can supervise many employees.  

```text
Employee  M ─── managed by ─── 1  Employee
