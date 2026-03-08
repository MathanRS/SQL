# 1327. List the Products Ordered in a Period

**Link**: [Problem Link](https://leetcode.com/problems/list-the-products-ordered-in-a-period/description/)

```sql
SELECT 
    p.product_name,
    SUM(unit) AS unit
FROM Products p
JOIN Orders o
    ON p.product_id = o.product_id
WHERE MONTH(order_date) = 2
  AND YEAR(order_date) = 2020
GROUP BY 1
HAVING unit >= 100;