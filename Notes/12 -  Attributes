## ERD Attributes  
> Adapted from Mohammed Abu-Hadhoud’s “Attributes” slide deck (2023). :contentReference[oaicite:0]{index=0}  

### 1 · What Is an Attribute?  
An **attribute** represents a property that describes an entity.  
In an ER diagram it is drawn as an **oval** connected to its entity rectangle.  


---

### 2 · Types of Attributes  

| Type | ERD Icon | Definition | Slide Example |
|------|----------|------------|---------------|
| **Key Attribute** | Oval with **underlined** name | Uniquely identifies each entity instance. | `Student.ID` |
| **Composite Attribute** | Oval that branches into sub-ovals | Composed of smaller attributes. | `Name → First, Mid, Last` |
| **Multivalued Attribute** | **Double-lined** oval | Can hold multiple values for one entity. | `PhoneNos` |
| **Derived Attribute** | **Dashed** oval | Calculated from other attributes. | `Age` derived from `BirthDate` |

---

#### 2.1 Key Attribute  
*Text underlined in the diagram*—e.g., **ID** uniquely picks one student from the set.  

#### 2.2 Composite Attribute  
The parent oval (*Name*) splits into its components.  

#### 2.3 Multivalued Attribute  
Double border signals many values: a student may list several phone numbers.  

#### 2.4 Derived Attribute  
Dashed oval shows the value is computed, not stored—*Age* = current date − *BirthDate*.  

---

### 3 · Why Classify Attributes?  
1. **Design clarity** – distinguishes stored vs calculated data.  
2. **Normalization guide** – composite fields may need splitting into separate columns.  
3. **Integrity & indexing** – key attributes become primary keys; multivalued attributes may require child tables.  

---

