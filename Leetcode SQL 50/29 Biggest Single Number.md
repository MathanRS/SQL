# 619. Biggest Single Number

**Link**: [Problem Link](https://leetcode.com/problems/biggest-single-number/description/)

```sql
SELECT MAX(num) AS num
FROM (
    SELECT num
    FROM MyNumbers
    GROUP BY num
    HAVING COUNT(*) = 1
) t;