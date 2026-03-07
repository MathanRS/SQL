### 1378. Replace Employee ID With The Unique Identifier
**Link** : [Problem Link](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT unique_id, name
FROM Employees E
LEFT JOIN EmployeeUNI EU
ON E.id = EU.id;
```