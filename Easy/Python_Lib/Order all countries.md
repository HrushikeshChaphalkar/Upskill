**Question:**

Order all countries by the year they first participated in the Olympics.

Output the National Olympics Committee (NOC) name along with the desired year.

Sort records by the year and the NOC in ascending order.

---
**Solution:**
```python
result = (
    olympics_athletes_events.groupby(['noc'])['year']
    .min()
    )
    
result = (
    result.to_frame('first_time_year')
    .reset_index()
    .sort_values(['first_time_year', 'noc'])
    )
```