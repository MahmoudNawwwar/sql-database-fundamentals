## ERD Symbols  
> Adapted from Mohammed Abu-Hadhoud’s “ERD Symbols” slide deck (2023). :contentReference[oaicite:0]{index=0}  

### 1 · Core Shapes & Their Meanings  

| Symbol&nbsp;(Shape) | Purpose | Example in an ERD |
|---------------------|---------|-------------------|
| **Rectangle** | **Entity** type (table) | `Student`, `Course`, `Professor` |
| **Double Rectangle** | **Weak entity** (depends on another entity’s PK) | `Payment Detail` under `Invoice` |
| **Diamond** | **Relationship** between entities | `Enrolled`, `Teaches`, `Mentors` |
| **Oval** | **Attribute** of an entity | `Name`, `BirthDate`, `CreditHours` |
| **Double Oval** | **Multivalued attribute** | `PhoneNumber` (can store multiple numbers) |
| **Dashed Oval** | **Derived attribute** (calculated) | `Age` derived from `BirthDate` |
| **Underline** inside an oval | Marks a **Primary Key** attribute | `Student.ID` |  

---

### 2 · Quick Reference Cheat-Sheet  

| Icon | You may see it… | Interpretation |
|------|-----------------|----------------|
| ▭ (rectangle) | Around nouns | “This is a thing/table.” |
| ◊ (diamond) | Between two rectangles | “These things relate.” |
| ○ (oval) | Hanging off a rectangle | “This is a property of that thing.” |
| ○○ (double-lined oval) | Two concentric ovals | “One row can have **many** of these values.” |
| ╌○ (dashed oval) | Dashed border | “Not stored—computed on demand.” |
| ▭▭ (double rectangle) | Shadowed rectangle | “Needs its parent to exist (weak).” |

---

### 3 · Reading Example (from the slides)  

* **Entities**: `Student`, `Course`.  
* **Relationship**: `Enrolled` (many-to-many).  
* **Cardinality**: crow-feet indicate “many,” single line means “one.”  
* **Attributes**: `ID`, `Name`, `PhoneNumber`, `Age`, `CreditHours`.  
* `PhoneNumber` is multivalued, `Age` is derived, and `ID` is the PK.

---

### 4 · Why Memorize These Symbols?  

1. **Universal Vocabulary** – Most ER-drawing tools (Draw.io, Lucidchart, ERDPlus) follow the same iconography.  
2. **Faster Diagramming** – Recognizing a double oval instantly tells you the attribute can repeat, saving annotations.  
3. **Clear Communication** – Stakeholders can spot PKs, weak entities, and derived fields without reading footnotes.  

---


