# Workers With The Highest Salaries

**Question:**
Management wants to analyze only employees with official job titles. Find the job titles of the employees with the highest salary. If multiple employees have the same highest salary, include all their job titles.

**Tables:** `worker`, `title`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/10353-workers-with-the-highest-salaries?code_type=3)

---

## Approach
```sql
SELECT t.worker_title
FROM (
    SELECT worker_id, salary, department, t.worker_title,
           DENSE_RANK() OVER(ORDER BY salary DESC) AS rankk
    FROM worker w
    JOIN title t
        ON w.worker_id = t.worker_ref_id
) t
WHERE rankk = 1;
```