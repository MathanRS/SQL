### 620. Not Boring Movies
**Link** : [Problem Link](https://leetcode.com/problems/not-boring-movies/description/)

```sql
SELECT *
FROM Cinema
WHERE MOD(id, 2) <> 0
  AND description <> 'boring'
ORDER BY rating DESC;