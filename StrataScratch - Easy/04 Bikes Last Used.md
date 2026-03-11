# Bikes Last Used

**Question:**
Find the last time each bike was in use. Output both the bike number and the date-timestamp of the bike's last use (i.e., the date-time the bike was returned). Order the results by bikes that were most recently used.

**Tables:** `dc_bikeshare_q1_2012`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/10176-bikes-last-used?code_type=3)

---

## Approach
```sql
SELECT bike_number, MAX(end_time) AS last_used
FROM dc_bikeshare_q1_2012
GROUP BY bike_number
ORDER BY last_used DESC;
```