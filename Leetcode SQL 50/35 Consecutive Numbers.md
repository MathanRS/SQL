# 180. Consecutive Numbers

**Link**: [Problem Link](https://leetcode.com/problems/consecutive-numbers/description/)

```sql
SELECT DISTINCT
    (CASE 
        WHEN num = prev1 AND num = prev2 
        THEN num 
    END) AS ConsecutiveNums
FROM (
    SELECT 
        id,
        num,
        LAG(num, 1) OVER (ORDER BY id) AS prev1,
        LAG(num, 2) OVER (ORDER BY id) AS prev2
    FROM Logs
) t
WHERE (CASE 
        WHEN num = prev1 AND num = prev2 
        THEN num 
      END) IS NOT NULL;