# 1174. Immediate Food Delivery II

**Link**: [Problem Link](https://leetcode.com/problems/immediate-food-delivery-ii/description/)

```sql
SELECT 
ROUND(
    SUM(CASE 
        WHEN order_date = customer_pref_delivery_date THEN 1
        ELSE 0 
    END) / COUNT(customer_id) * 100,
2) AS immediate_percentage
FROM (
    SELECT 
        delivery_id,
        customer_id,
        order_date,
        customer_pref_delivery_date,
        RANK() OVER (PARTITION BY customer_id ORDER BY order_date) AS ranky
    FROM Delivery
) t
WHERE ranky = 1;