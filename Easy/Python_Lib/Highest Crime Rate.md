**Question:**

Find the number of crime occurrences for each day of the week.
Output the day alongside the corresponding crime count.

-------------------------------------------------------------------
**Solution:**
```python
result = (
    sf_crime_incidents_2014_01.groupby(['day_of_week'])
    .size()
    .to_frame('n_occurences')
    .reset_index()
    .sort_values('n_occurences', ascending = False)
    )
```