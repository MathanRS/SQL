# Most Profitable Financial Company

**Question:**
Find the most profitable company from the financial sector. Output the result along with the continent.

**Tables:** `forbes_global_2010_2014`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9663-find-the-most-profitable-company-in-the-financial-sector-of-the-entire-world-along-with-its-continent?code_type=3)

---

## Approach
```sql
SELECT company, continent
FROM forbes_global_2010_2014
WHERE profits = (
    SELECT MAX(profits)
    FROM forbes_global_2010_2014
    WHERE sector = 'Financials'
);
```