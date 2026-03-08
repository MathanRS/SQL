# 176. Second Highest Salary

**Link**: [Problem Link](https://leetcode.com/problems/second-highest-salary/)

```sql
SELECT 
    MAX(CASE WHEN rankk = 2 THEN salary ELSE NULL END) AS SecondHighestSalary
FROM (
    SELECT 
        id,
        salary,
        DENSE_RANK() OVER (ORDER BY salary DESC) AS rankk
    FROM Employee
) t;