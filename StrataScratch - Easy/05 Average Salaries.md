# Average Salaries

**Question:**
Compare each employee's salary with the average salary of the corresponding department. Output the department, first name, and salary of employees along with the average salary of that department.

**Tables:** `employee`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9917-average-salaries?code_type=3)

---

## Approach
```sql
SELECT department, first_name, salary,
       AVG(salary) OVER(PARTITION BY department) AS avg_salary
FROM employee;
```