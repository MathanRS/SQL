# MacBookPro User Event Count

**Question:**
Count the number of user events performed by MacBookPro users. Output the result along with the event name. Sort the result based on the event count in the descending order.

**Tables:** `playbook_events`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9653-count-the-number-of-user-events-performed-by-macbookpro-users?code_type=3)

---

## Approach
```sql
SELECT event_name, COUNT(device) AS event_count
FROM playbook_events
GROUP BY device, event_name
HAVING device = 'macbook pro'
ORDER BY event_count DESC;
```