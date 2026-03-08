# 185. Department Top Three Salaries

**Link**: [Problem Link](https://leetcode.com/problems/department-top-three-salaries/)

```sql
SELECT Department, Employee, Salary
FROM (
    SELECT 
        E.id,
        E.name AS Employee,
        salary,
        D.name AS Department,
        DENSE_RANK() OVER (PARTITION BY D.name ORDER BY salary DESC) AS rankk
    FROM Employee E
    JOIN Department D
        ON E.departmentId = D.id
) t
WHERE rankk <= 3;