# 1321. Restaurant Growth

**Link**: [Problem Link](https://leetcode.com/problems/restaurant-growth/description/)

```sql
SELECT DISTINCT visited_on, amount, average_amount
FROM (
    SELECT 
        visited_on,
        SUM(amount) OVER (
            ORDER BY visited_on 
            RANGE BETWEEN INTERVAL 6 DAY PRECEDING AND CURRENT ROW
        ) AS amount,
        ROUND(
            SUM(amount) OVER (
                ORDER BY visited_on 
                RANGE BETWEEN INTERVAL 6 DAY PRECEDING AND CURRENT ROW
            ) / 7, 
        2) AS average_amount
    FROM (
        SELECT visited_on, SUM(amount) AS amount
        FROM Customer
        GROUP BY 1
    ) daily
    GROUP BY visited_on
) z
WHERE visited_on >= (
    SELECT MIN(visited_on) + INTERVAL 6 DAY 
    FROM Customer
)
ORDER BY visited_on;