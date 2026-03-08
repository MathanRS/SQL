# 196. Delete Duplicate Emails

**Link**: [Problem Link](https://leetcode.com/problems/delete-duplicate-emails/description/)

```sql
WITH ranked AS (
    SELECT 
        id,
        RANK() OVER (PARTITION BY email ORDER BY id) AS rn
    FROM Person
)
DELETE FROM Person
WHERE id IN (
    SELECT id
    FROM ranked
    WHERE rn > 1
);