## ERD – What Is It & Why Use It?  
> Adapted from Mohammed Abu-Hadhoud’s “What is ERD and Why?” slide deck (2023). :contentReference[oaicite:0]{index=0}  

### 1 · Definition  
An **Entity-Relationship Diagram (ERD)** is a pictorial representation that explains how entities in a database are related.  
* Acts as the **structural blueprint** of the database before implementation.  
* Built around three core components: **entities, attributes, relationships**.  

### 2 · ER Model vs ERD  
| Concept | Description |
|---------|-------------|
| **ER Model** | The underlying **conceptual data model** derived from business requirements. |
| **ER Diagram** | The **visual diagram** that illustrates that model for designers and stakeholders. |

### 3 · Key Components  
| Symbol | Meaning | Example from slides |
|--------|---------|---------------------|
| Rectangle | **Entity** | `Student`, `Course`, `Professor` |
| Oval      | **Attribute** | `ID`, `Name`, `BirthDate`, `CreditHours` |
| Diamond   | **Relationship** | `Enrolled in`, `Teaches`, `Mentors` |
| Lines w/ crow-feet | **Cardinality** | `M:N`, `1:M`, `1:1` |  

*Diagram snippet:*  
`Student 1..M — Enrolled — M..1 Course`  
`Professor 1..M — Teaches — M..1 Course`  
`Professor 1 — Mentors — 0..M Student`  

### 4 · Why Use ER Diagrams?  
1. **Conceptualization** – quick visual of which fields belong to which entity.  
2. **Complexity reduction** – simplifies large systems, making design iterations faster.  
3. **Early validation** – lets stakeholders preview the schema and catch issues before coding.  
4. **Documentation** – serves as living reference for developers and DBAs.  
5. **Dat**
