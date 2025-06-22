# Total vs Partial Participation  
> Adapted from Mohammed Abu-Hadhoud’s “Total vs Partial Participation” slide deck (2023).

---

## 1 · Definition  

| Term | Meaning | ERD Line Style |
|------|---------|----------------|
| **Total Participation** | **Every** instance of Entity A **must** participate in the relationship with Entity B. | **Double** line from entity to relationship diamond |
| **Partial Participation** | **Some** instances of Entity A **may** participate; the link is optional. | **Single** line from entity to relationship diamond |

---

## 2 · Slide Examples  

| Relationship | Participation on A | Participation on B | Interpretation |
|--------------|-------------------|--------------------|----------------|
| **Employee** *works in* **Department** | **Total** | Partial | Every employee must belong to one department; a department can exist before hiring employees. |
| **Department** *manages* **Project** | Partial | **Total** | A department may manage zero or many projects; every project **must** have a managing department. |

*Notation (crow’s-foot + line style)*  

