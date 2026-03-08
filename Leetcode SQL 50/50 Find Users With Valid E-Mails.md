# 1517. Find Users With Valid E-Mails

**Link**: [Problem Link](https://leetcode.com/problems/find-users-with-valid-e-mails/description/)

```sql
SELECT user_id, name, mail
FROM Users
WHERE REGEXP_LIKE(mail, '^[A-Za-z][A-Za-z0-9._-]*@leetcode[.]com$', 'c');