# 1141. User Activity for the Past 30 Days I

**Link**: [Problem Link](https://leetcode.com/problems/user-activity-for-the-past-30-days-i/description/)

```sql
SELECT 
    u1.activity_date AS `day`,
    COUNT(DISTINCT u1.user_id) AS active_users
FROM Activity u1
WHERE activity_date BETWEEN '2019-06-28' AND '2019-07-27'
GROUP BY 1;