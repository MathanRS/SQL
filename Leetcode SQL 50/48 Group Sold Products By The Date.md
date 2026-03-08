# 1484. Group Sold Products By The Date

**Link**: [Problem Link](https://leetcode.com/problems/group-sold-products-by-the-date/)

```sql
SELECT 
    sell_date,
    COUNT(DISTINCT product) AS num_sold,
    GROUP_CONCAT(DISTINCT product ORDER BY product) AS products
FROM Activities
GROUP BY sell_date;