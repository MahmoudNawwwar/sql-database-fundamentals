# Cardinality vs Ordinality  
> Adapted from Mohammed Abu-Hadhoud’s “Cardinality vs Ordinality” slide deck (2023).

---

## 1 · Two Numbers for Every Relationship  

| Term | Tells You | Nickname in Slides |
|------|-----------|--------------------|
| **Cardinality (Max)** | The **maximum** number of times one row in Entity A can relate to rows in Entity B. | “Max” |
| **Ordinality (Min)**  | The **minimum** (required) number of times a row in Entity A must relate to rows in Entity B. | “Min / optional-mandatory flag” |

---

## 2 · Classic Examples from the Slides  

| Relationship | (Min, Max) on A | (Min, Max) on B | Interpretation |
|--------------|-----------------|-----------------|----------------|
| **Student**–**Course** (*Enrolled*) | (0, M) | (0, M) | A student **may** enroll in many courses, but can skip all; a course **may** have many students or none. |
| **Customer**–**Order** (*Place*) | (1, 1) | (0, M) | Each customer **must** have at least one order; an order belongs to exactly one customer. |

Diagram style used in slides:  

