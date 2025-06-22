# Many-to-Many (M : N) Relationship  
> Adapted from Mohammed Abu-Hadhoud’s “Many-to-Many Relationship” slide deck (2023).

---

## 1 · Definition  
A **many-to-many (M : N) relationship** links two entities so that  
*each instance of Entity A can relate to multiple instances of Entity B,  
and each instance of Entity B can relate to multiple instances of Entity A*. :contentReference[oaicite:1]{index=1}  

---

## 2 · Slide Examples  

| Entities | Relationship | Business Rule |
|----------|--------------|---------------|
| **Student** ↔ **Course** | **Enrolled** | • A student may enroll in many courses.<br>• A course may include many students. |
| **Order** ↔ **Product** | **Contains / Placed In** | • An order can contain many products.<br>• A product can appear in many orders. | :contentReference[oaicite:2]{index=2}  

---

## 3 · ER-Diagram Notation  

