# Unique Users Per Client Per Month

**Question:**
Write a query that returns the number of unique users per client for each month. Assume all events occur within the same year, so only month needs to be in the output as a number from 1 to 12.

**Tables:** `fact_events`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/2024-unique-users-per-client-per-month?code_type=3)

---

## Approach
```sql
SELECT client_id,
       MONTH(time_id) AS `month`,
       COUNT(DISTINCT(user_id)) AS users_num
FROM fact_events
GROUP BY client_id, MONTH(time_id)
ORDER BY client_id, month;
```