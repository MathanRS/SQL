# 1045. Customers Who Bought All Products

**Link**: [Problem Link](https://leetcode.com/problems/customers-who-bought-all-products/description/)

```sql
SELECT DISTINCT customer_id
FROM Customer c
GROUP BY customer_id
HAVING COUNT(DISTINCT product_key) = (
    SELECT COUNT(DISTINCT product_key)
    FROM Product
);