# Cardinality Symbols & Practices  
> Adapted from Mohammed Abu-Hadhoud’s “Cardinality Symbols and Practices” slide deck (2023).

---

## 1 · Purpose  
Cardinality symbols let you read an ER diagram at a glance—showing **how many** rows in one table may (or must) relate to rows in another. The deck compares the three most common notations. :contentReference[oaicite:1]{index=1}  

---

## 2 · The Big Three Notations  

| Notation | Where You’ll See It | Visual Cue | Sample (Customer–Order) |
|----------|---------------------|------------|-------------------------|
| **Crow’s-Foot** | Lucidchart, ERDPlus, MySQL Workbench | Single line ↔ crow-foot | `Customer 1 ────< Order` |
| **Min-Max** | Chen diagrams; academic texts | `(min,max)` labels | `(1,1)` next to Customer, `(0,M)` next to Order |
| **Bachman** | Older CASE tools (ERwin Classic) | Dot & dash symbols | Dot at “1” end, three dashes at “many” end |

---

## 3 · Crow’s-Foot Symbols  

| Symbol | Meaning |
|--------|---------|
| **Single line** | Exactly one |
| **Circle** • | Zero allowed (optional) |
| **Crow-Foot** < | Many |
| **Combination** •< | Zero or many `(0..M)` |
| **Line + Crow-Foot** | One or many `(1..M)` |

*Example*:  

