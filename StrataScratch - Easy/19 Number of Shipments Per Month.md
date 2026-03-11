# Number of Shipments Per Month

**Question:**
Write a query that will calculate the number of shipments per month. The unique key for one shipment is a combination of `shipment_id` and `sub_id`. Output the `year_month` in format `YYYY-MM` and the number of shipments in that month.

**Tables:** `amazon_shipment`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/2056-number-of-shipments-per-month?code_type=3)

---

## Approach
```sql
SELECT
    COUNT(DISTINCT CONCAT(shipment_id, '+', sub_id)) AS `count(shipment_id)`,
    DATE_FORMAT(shipment_date, '%Y-%m') AS date_ym
FROM amazon_shipment
GROUP BY date_ym
ORDER BY date_ym;
```