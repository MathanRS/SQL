### 1280. Students and Examinations
**Link** : [Problem Link](https://leetcode.com/problems/students-and-examinations/description/)

```sql
SELECT s.student_id,
       s.student_name,
       su.subject_name,
       COUNT(e.subject_name) AS attended_exams
FROM Students s
CROSS JOIN Subjects su
LEFT JOIN Examinations e
   ON e.subject_name = su.subject_name
  AND e.student_id = s.student_id
GROUP BY s.student_id, s.student_name, su.subject_name
ORDER BY s.student_id, su.subject_name;