# 1070. Product Sales Analysis III

**Link**: [Problem Link](https://leetcode.com/problems/product-sales-analysis-iii/description/)

```sql
SELECT product_id, `year` AS first_year, quantity, price
FROM (
    SELECT 
        product_id,
        `year`,
        quantity,
        price,
        RANK() OVER (PARTITION BY product_id ORDER BY `year`) AS rankk
    FROM Sales
) t
WHERE rankk = 1;