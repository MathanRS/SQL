### 1068. Product Sales Analysis I
**Link** : [Problem Link](https://leetcode.com/problems/product-sales-analysis-i/?envType=study-plan-v2&envId=top-sql-50)

```sql
SELECT P.product_name, S.`year`, S.price
FROM Sales S
INNER JOIN Product P
ON S.product_id = P.product_id;
```