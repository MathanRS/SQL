# 602. Friend Requests II: Who Has the Most Friends

**Link**: [Problem Link](https://leetcode.com/problems/friend-requests-ii-who-has-the-most-friends/description/)

```sql
SELECT id, num
FROM (
    SELECT 
        id,
        COUNT(*) AS num,
        DENSE_RANK() OVER (ORDER BY COUNT(*) DESC) AS rnk
    FROM (
        SELECT requester_id AS id FROM RequestAccepted
        UNION ALL
        SELECT accepter_id FROM RequestAccepted
    ) x
    GROUP BY 1
) z
WHERE rnk = 1;