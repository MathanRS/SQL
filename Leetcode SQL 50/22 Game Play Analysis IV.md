# 550. Game Play Analysis IV

**Link**: [Problem Link](https://leetcode.com/problems/game-play-analysis-iv/description/)

```sql
SELECT ROUND(
    (
        SELECT COUNT(*)
        FROM (
            SELECT 
                player_id,
                event_date,
                LEAD(event_date) OVER (PARTITION BY player_id ORDER BY event_date) AS next_day,
                ROW_NUMBER() OVER (PARTITION BY player_id ORDER BY event_date) AS ranky
            FROM Activity
        ) t
        WHERE ranky = 1
        AND event_date = next_day - INTERVAL 1 DAY
    ) * 1.0
    /
    (
        SELECT COUNT(DISTINCT player_id) 
        FROM Activity
    ),
2) AS fraction;