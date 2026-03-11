# Workers by Department Since April

**Question:**
Find the number of workers by department who joined on or after April 1, 2014. Output the department name along with the corresponding number of workers. Sort the results based on the number of workers in descending order.

**Tables:** `worker`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9847-find-the-number-of-workers-by-department?code_type=3)

---

## Approach
```sql
SELECT
    department,
    COUNT(*)
FROM worker
WHERE joining_date >= '2014-04-01'
GROUP BY department;
```