## Components of an ER Diagram  
> Adapted from Mohammed Abu-Hadhoud’s “Components of ER Diagram” slide deck (2023). :contentReference[oaicite:0]{index=0}  

### 1 · The Three Pillars  

| Pillar | Core Items | Quick Definition |
|--------|------------|------------------|
| **Entities** | • Strong entity<br>• Weak entity | Real-world objects or concepts stored as tables. |
| **Attributes** | • Simple attribute<br>• Key attribute<br>• Composite attribute<br>• Multivalued attribute<br>• Derived attribute | Properties that describe an entity. |
| **Relationships** | • One-to-One (1:1)<br>• One-to-Many (1:M)<br>• Many-to-One (M:1)<br>• Many-to-Many (M:N) | How entities interact or are linked. |

---

### 2 · Entities  

| Type | Icon | Description |
|------|------|-------------|
| **Strong Entity** | Single rectangle | Has its own primary key; exists independently. |
| **Weak Entity**  | Double rectangle | Depends on a strong entity’s key for identity. |

---

### 3 · Attributes  

| Attribute Kind | Icon | Purpose |
|----------------|------|---------|
| **Simple (atomic)**   | Single oval | Cannot be further divided (e.g., `Salary`). |
| **Key Attribute**     | Underlined oval | Participates in the primary key (`StudentID`). |
| **Composite**         | Oval branching to sub-ovals | Breaks into smaller parts (`Address → Street, City, Zip`). |
| **Multivalued**       | Double-lined oval | May hold multiple values (`PhoneNumber`). |
| **Derived**           | Dashed oval | Calculated on the fly (`Age` from `BirthDate`). |

---

### 4 · Relationships & Cardinalities  

| Relationship | Cardinality | Real-World Example |
|--------------|-------------|--------------------|
| **One-to-One**  | 1:1 | `Person` ↔ `Passport` |
| **One-to-Many** | 1:M | `Department` → `Employee` |
| **Many-to-One** | M:1 | `Employee` → `Department` (child-to-parent view) |
| **Many-to-Many**| M:N | `Student` ↔ `Course` |

*Crow-feet notation* in ERDs visually shows these cardinalities.

---

### 5 · Putting It All Together  

