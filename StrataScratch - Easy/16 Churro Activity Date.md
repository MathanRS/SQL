# Churro Activity Date

**Question:**
Find the inspection date and risk category (`pe_description`) of facilities named 'STREET CHURROS' that received a score below 95.

**Tables:** `los_angeles_restaurant_health_inspections`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9688-churro-activity-date?code_type=3)

---

## Approach
```sql
SELECT activity_date, pe_description
FROM los_angeles_restaurant_health_inspections
WHERE facility_name = 'STREET CHURROS'
  AND score < 95;
```