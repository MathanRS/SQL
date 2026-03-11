# Salaries Differences

**Question:**
Calculate the difference between the highest salaries in the marketing and engineering departments. Output just the absolute difference in salaries.

**Tables:** `db_employee`, `db_dept`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/10308-salaries-differences?code_type=3)

---

## Approach
```sql
SELECT 
  ABS(
    MAX(CASE WHEN d.department = 'Engineering' THEN e.salary END) - 
    MAX(CASE WHEN d.department = 'Marketing' THEN e.salary END)
  ) AS salary_difference 
FROM db_employee e
JOIN db_dept d ON e.department_id = d.id;
```