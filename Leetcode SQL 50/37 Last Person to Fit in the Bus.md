# 1204. Last Person to Fit in the Bus

**Link**: [Problem Link](https://leetcode.com/problems/last-person-to-fit-in-the-bus/)

```sql
SELECT person_name
FROM (
    SELECT 
        person_id,
        turn,
        person_name,
        weight,
        SUM(weight) OVER (ORDER BY turn) AS total
    FROM Queue
    GROUP BY turn
) t
WHERE total <= 1000
ORDER BY turn DESC
LIMIT 1;