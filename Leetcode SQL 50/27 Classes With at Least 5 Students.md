# 596. Classes With at Least 5 Students

**Link**: [Problem Link](https://leetcode.com/problems/classes-with-at-least-5-students/description/)

```sql
SELECT class
FROM (
    SELECT 
        COUNT(*) AS `count`,
        class
    FROM Courses
    GROUP BY class
) t
WHERE `count` >= 5;