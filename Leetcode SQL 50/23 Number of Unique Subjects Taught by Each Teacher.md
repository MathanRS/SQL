# 2356. Number of Unique Subjects Taught by Each Teacher

**Link**: [Problem Link](https://leetcode.com/problems/number-of-unique-subjects-taught-by-each-teacher/description/)

```sql
SELECT teacher_id, COUNT(DISTINCT subject_id) AS cnt
FROM Teacher
GROUP BY 1;