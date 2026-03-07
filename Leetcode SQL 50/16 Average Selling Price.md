### 1251. Average Selling Price
**Link** : [Problem Link](https://leetcode.com/problems/average-selling-price/description/)

```sql
SELECT p.product_id,
       CASE
           WHEN SUM(u.units) > 0 THEN ROUND((SUM(units * price) / SUM(units)), 2)
           WHEN SUM(u.units) IS NULL THEN 0
       END AS average_price
FROM Prices p
LEFT JOIN UnitsSold u
   ON p.product_id = u.product_id
  AND purchase_date BETWEEN start_date AND end_date
GROUP BY p.product_id;