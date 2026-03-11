# Finding Updated Records

**Question:**
We have a table with employees and their salaries; however, some of the records are old and contain outdated salary information. Since there is no timestamp, assume salary is non-decreasing over time. You can consider the current salary for an employee is the largest salary value among their records. If multiple records share the same maximum salary, return any one of them. Output their id, first name, last name, department ID, and current salary. Order your list by employee ID in ascending order.

**Tables:** `ms_employee_salary`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/10299-finding-updated-records?code_type=3)

---

## Approach 1
```sql
SELECT id,
       first_name,
       last_name,
       department_id,
       salary
FROM (
  SELECT *,
         ROW_NUMBER() OVER (PARTITION BY id ORDER BY salary DESC, department_id DESC) AS rn
  FROM ms_employee_salary
) s
WHERE rn = 1
ORDER BY id ASC;
```
## Approach 2
```sql
SELECT id, first_name, last_name, department_id, MAX(salary)
FROM ms_employee_salary
GROUP BY id;