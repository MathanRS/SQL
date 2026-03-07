### 570. Managers with at Least 5 Direct Reports
**Link** : [Problem Link](https://leetcode.com/problems/managers-with-at-least-5-direct-reports/description/)

```sql
SELECT e2.name
FROM Employee e1
JOIN Employee e2
   ON e1.managerId = e2.id
GROUP BY e2.name, e1.managerId
HAVING COUNT(*) > 4;