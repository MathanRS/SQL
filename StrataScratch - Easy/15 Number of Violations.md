# Number of Violations

**Question:**
You are given a dataset of health inspections that includes details about violations. Each row represents an inspection, and if an inspection resulted in a violation, the `violation_id` column will contain a value. Count the total number of violations that occurred at 'Roxanne Cafe' for each year, based on the inspection date. Output the year and the corresponding number of violations in ascending order of the year.

**Tables:** `sf_restaurant_health_violations`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9728-inspections-that-resulted-in-violations?code_type=3)

---

## Approach
```sql
SELECT YEAR(inspection_date) AS inspection_year,
       COUNT(*) AS n_violations
FROM sf_restaurant_health_violations
WHERE violation_id IS NOT NULL
  AND business_name = 'Roxanne Cafe'
GROUP BY inspection_year
ORDER BY inspection_year ASC;
```