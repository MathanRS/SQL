# 1789. Primary Department for Each Employee

**Link**: [Problem Link](https://leetcode.com/problems/primary-department-for-each-employee/)

```sql
SELECT 
    employee_id,
    CASE 
        WHEN SUM(CASE WHEN primary_flag = 'Y' THEN 1 ELSE 0 END) > 0
            THEN MAX(CASE WHEN primary_flag = 'Y' THEN department_id END)
        WHEN SUM(CASE WHEN primary_flag = 'N' THEN 1 ELSE 0 END) = 1
            THEN MAX(CASE WHEN primary_flag = 'N' THEN department_id END)
    END AS department_id
FROM Employee
GROUP BY employee_id;