# 1164. Product Price at a Given Date

**Link**: [Problem Link](https://leetcode.com/problems/product-price-at-a-given-date/description/)

```sql
SELECT main.product_id, COALESCE(price, 10) AS price
FROM (
    SELECT DISTINCT product_id
    FROM Products
) AS main
LEFT JOIN (
    SELECT product_id, price
    FROM (
        SELECT 
            product_id,
            new_price AS price,
            change_date,
            ROW_NUMBER() OVER (PARTITION BY product_id ORDER BY change_date DESC) AS rankk
        FROM Products
        WHERE change_date <= '2019-08-16'
    ) t
    WHERE rankk = 1
) x
ON main.product_id = x.product_id;