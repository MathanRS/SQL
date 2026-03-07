# 41. Movie Rating

**Link**: [Problem Link](https://leetcode.com/problems/movie-rating/description/)

```sql
(SELECT name as results
FROM Users u 
JOIN MovieRating mr ON u.user_id = mr.user_id
GROUP BY u.user_id 
ORDER BY COUNT(mr.user_id) DESC, name ASC
LIMIT 1) 
UNION ALL
(SELECT m1.title
FROM MOVIES m1
JOIN MovieRating mr2
ON m1.movie_id = mr2.movie_id
WHERE MONTH(created_at) = 2 AND YEAR(created_at) = 2020
GROUP BY m1.movie_id
ORDER BY AVG(mr2.rating) DESC, 1 ASC
LIMIT 1);
```
