### 577. Employee Bonus
**Link** : [Problem Link](https://leetcode.com/problems/employee-bonus/description/)

```sql
SELECT name, bonus
FROM Employee E
LEFT JOIN Bonus B
   ON E.empID = B.empID
WHERE bonus < 1000
   OR bonus IS NULL;