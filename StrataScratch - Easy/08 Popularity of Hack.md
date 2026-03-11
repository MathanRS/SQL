# Popularity of Hack

**Question:**
Meta/Facebook has developed a new programing language called Hack. To measure the popularity of Hack they ran a survey with their employees. The survey included data on previous programing familiarity as well as the number of years of experience, age, gender and most importantly satisfaction with Hack. Due to an error location data was not collected, but your supervisor demands a report showing average popularity of Hack by office location. Luckily the user IDs of employees completing the surveys were stored. Based on the above, find the average popularity of the Hack per office location. Output the location along with the average popularity.

**Tables:** `facebook_employees`, `facebook_hack_survey`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/10061-popularity-of-hack?code_type=3)

---

## Approach
```sql
SELECT
    f1.location,
    (SUM(f2.popularity) / COUNT(popularity)) AS avg_popularity
FROM facebook_employees AS f1
INNER JOIN facebook_hack_survey AS f2
    ON f1.id = f2.employee_id
GROUP BY f1.location;
```