# April Admin Employees

**Question:**
Find the number of employees working in the Admin department that joined in April or later, in any year.

**Tables:** `worker`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9845-find-the-number-of-employees-working-in-the-admin-department?code_type=3)

---

## Approach
```sql
SELECT COUNT(*) AS n_admins
FROM worker
WHERE MONTH(joining_date) >= 04
GROUP BY department
HAVING department = 'Admin';
```