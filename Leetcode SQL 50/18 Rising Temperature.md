# 197. Rising Temperature

**Link**: [Problem Link](https://leetcode.com/problems/rising-temperature/)

```sql
SELECT Id
FROM (
    SELECT 
        id AS Id,
        temperature,
        recordDate,
        temperature AS currenttemp,
        LAG(temperature) OVER (ORDER BY recordDate) AS prevtemp,
        LAG(recordDate) OVER (ORDER BY recordDate) AS prevDate
    FROM Weather
) t
WHERE prevtemp < currenttemp
AND recordDate = prevDate + INTERVAL 1 DAY;