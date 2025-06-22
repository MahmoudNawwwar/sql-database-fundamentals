# Building an ERD – Step-by-Step (Small University Project)  
> Adapted from Mohammed Abu-Hadhoud’s slide deck **“Process of Creating ERD Step by Step – Small Project”** (2023). :contentReference[oaicite:0]{index=0}  

---

## 1 · Overview of the Five Steps

| Step | Goal | Output |
|------|------|--------|
| **1. Entity Identification** | List the main business objects. | `Student`, `Course`, `Professor` |
| **2. Relationship Identification** | Link entities with verbs. | `Enrolled`, `Mentor`, `Teaches` |
| **3. Cardinality Identification** | Add min/max counts on each side. | e.g. `(0,M)` Student ↔ Course |
| **4. Attribute Identification** | Attach key and descriptive fields. | IDs, names, dates, etc. |
| **5. Draw the ERD** | Produce the visual diagram. | Crow’s-foot ERD |

---

## 2 · Project Requirements (from the slides)

* A **Student** can enroll in **many** courses; a **Course** can have **many** students.  
* Each student has **exactly one** mentor (**Professor**), but a professor can mentor many students.  
* A professor can teach **at most one** course; a course can have **at most one** professor.  
* Courses may have **no** professor yet; professors may teach **no** course. :contentReference[oaicite:1]{index=1}  

---

## 3 · Applying the Steps

### 3.1 Step 1 – Entities  
`Student`, `Course`, `Professor`

### 3.2 Step 2 – Relationships  

| Entities | Relationship | Verb |
|----------|--------------|------|
| Student ↔ Course | `Enrolled` | *enrolls in* |
| Student ↔ Professor | `Mentor` | *is mentored by* |
| Professor ↔ Course | `Teaches` | *teaches* |

### 3.3 Step 3 – Cardinalities  

| Relationship | Cardinality (Student / Professor / Course) |
|--------------|-------------------------------------------|
| Student – Course | `(0,M)` each side |
| Student – Professor | Student `(0,1)` ↔ Professor `(0,M)` |
| Professor – Course | Professor `(0,1)` ↔ Course `(0,1)` |

### 3.4 Step 4 – Attributes  

| Entity | Attributes (PK underlined, composite shown >) |
|--------|----------------------------------------------|
| **Student** | **ID**, >Name(First, Mid, Last), Gender, BirthDate, Age, Phone |
| **Course**  | **ID**, Name, CreditHours |
| **Professor** | **ID**, Name, Salary |
| **Enrolled** (relationship) | EnrollDate |

### 3.5 Step 5 – Final Crow’s-Foot ERD (textual)

Student |⎯⎯< (0,M) Enrolled (0,M) >⎯⎯| Course
│ │
│--ID (PK) │--ID (PK)
│--First, Mid, Last │--Name
│--Gender │--CreditHours
│--BirthDate └──────────────────
│--Age
│--Phone
│
|⎯⎯(0,1) Mentor (1,M)⎯⎯| Professor
│
│--ID (PK)
│--Name
│--Salary
|
|⎯⎯(0,1) Teaches (0,1)⎯⎯| Course

* **Double bar** in Crow’s-foot indicates mandatory `(1)`; circle indicates optional `(0)`; crow-foot indicates many `(M)`.  
* The `Enrolled` table (junction) resolves the many-to-many between `Student` and `Course`. :contentReference[oaicite:2]{index=2}  

---

## 4 · Key Takeaways

1. **Follow the five-step checklist**: Entities → Relationships → Cardinalities → Attributes → ERD.  
2. **Min/Max labels** (ordinality/cardinality) reveal optional vs mandatory links.  
3. **Junction tables** convert every M : N into two 1 : M relationships.  
4. Documenting the process makes the final ERD easier to validate with stakeholders before writing any SQL.  

