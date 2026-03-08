# 1729. Find Followers Count

**Link**: [Problem Link](https://leetcode.com/problems/find-followers-count/description/)

```sql
SELECT user_id, COUNT(user_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id;