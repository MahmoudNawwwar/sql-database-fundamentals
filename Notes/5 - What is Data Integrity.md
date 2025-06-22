# Data Integrity  
> Revision notes extracted from Mohammed Abu-Hadhoud’s **“What is Data Integrity?”** presentation (2023).  
> These notes are intended for second-pass revision and assume basic SQL knowledge. :contentReference[oaicite:0]{index=0}  

---

## 1 · Definition

* **Data integrity** is the accuracy, consistency, and reliability of data throughout its entire life-cycle—from creation to deletion.  
* It guarantees that data remain **complete, accurate, and trustworthy**. :contentReference[oaicite:1]{index=1}  

---

## 2 · Threats to Data Integrity

| Category | Typical Causes |
|----------|----------------|
| **Human error** | Manual data entry mistakes, accidental deletion |
| **Hardware / software failure** | Disk crashes, power loss, application bugs |
| **Security breaches** | Unauthorized updates, malicious tampering |
| **Transfer errors** | Network glitches, partial loads during ETL |

Maintaining integrity requires policies, procedures, and supporting technology (encryption, backups, access controls). :contentReference[oaicite:2]{index=2}  

---

## 3 · Key Types of Data Integrity

| Type | Purpose | Typical Implementation |
|------|---------|------------------------|
| **Entity in**
