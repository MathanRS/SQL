# Artist Appearance Count

**Question:**
Find how many times each artist appeared on the Spotify ranking list. Output the artist name along with the corresponding number of occurrences. Order records by the number of occurrences in descending order.

**Tables:** `spotify_worldwide_daily_song_ranking`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9992-find-artists-that-have-been-on-spotify-the-most-number-of-times?code_type=3)

---

## Approach
```sql
SELECT
    artist,
    COUNT(artist) AS n_occurences
FROM spotify_worldwide_daily_song_ranking
GROUP BY artist
ORDER BY n_occurences DESC;
```