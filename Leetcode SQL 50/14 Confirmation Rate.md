### 1934. Confirmation Rate
**Link** : [Problem Link](https://leetcode.com/problems/confirmation-rate/)

```sql
SELECT s.user_id,
       COALESCE(
           ROUND(
               COUNT(CASE WHEN action = 'confirmed' THEN 1 ELSE NULL END) 
               / COUNT(c.action), 2
           ), 0
       ) AS confirmation_rate
FROM Signups s
LEFT JOIN Confirmations c
   ON s.user_id = c.user_id
GROUP BY s.user_id;