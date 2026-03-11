# Customer Details

**Question:**
Find the details of each customer regardless of whether the customer made an order. Output the customer's first name, last name, and the city along with the order details. Sort records based on the customer's first name and the order details in ascending order.

**Tables:** `customers`, `orders`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9891-customer-details?code_type=3)

---

## Approach
```sql
SELECT
    first_name,
    last_name,
    city,
    order_details
FROM customers AS c
LEFT JOIN orders AS o
    ON c.id = o.cust_id
ORDER BY first_name ASC, order_details ASC;
```