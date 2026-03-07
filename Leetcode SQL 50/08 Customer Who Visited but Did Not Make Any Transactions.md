### 1581. Customer Who Visited but Did Not Make Any Transactions
**Link** : [Problem Link](https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/submissions/1937622183/)

```sql
SELECT V.customer_id, COUNT(V.customer_id) AS count_no_trans
FROM VISITS V
LEFT JOIN Transactions T
   ON V.visit_id = T.visit_id
WHERE T.transaction_id IS NULL
GROUP BY V.customer_id;