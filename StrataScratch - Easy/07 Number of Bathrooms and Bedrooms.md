# Number Of Bathrooms And Bedrooms

**Question:**
Find the average number of bathrooms and bedrooms for each city's property types. Output the result along with the city name and the property type.

**Tables:** `airbnb_search_details`

**QSTN Link:** [Stratscratch Problem](https://platform.stratascratch.com/coding/9622-number-of-bathrooms-and-bedrooms?code_type=3)

---

## Approach
```sql
SELECT city, property_type, AVG(bathrooms), AVG(bedrooms)
FROM airbnb_search_details
GROUP BY city, property_type;
```