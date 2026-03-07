### 1683. Invalid Tweets
**Link** : [Problem Link](https://leetcode.com/problems/invalid-tweets/description/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT tweet_id
FROM Tweets
WHERE LENGTH(content) > 15;
```