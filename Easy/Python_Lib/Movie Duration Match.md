

**Question:**

As a data scientist at Amazon Prime Video, you are tasked with enhancing the in-flight entertainment experience for Amazon’s airline partners. Your challenge is to develop a feature that suggests individual movies from Amazon's content database that fit within a given flight's duration. For flight 101, find movies whose runtime is less than or equal to the flight's duration.

The output should list suggested movies for the flight, including 'flight_id', 'movie_id', and 'movie_duration'."

---
**Solution:**
```python
import pandas as pd
output_col = ['flight_id', 'movie_id', 'movie_duration']

merge = pd.merge(flight_schedule, entertainment_catalog, how = 'cross')
merge.rename(columns={'duration': 'movie_duration'}, inplace=True)
merge.sort_values('movie_duration', inplace = True)

duration_filter = merge['flight_duration'] >= merge['movie_duration']
flight_no = merge['flight_id']==101
result = merge[flight_no & duration_filter][output_col]
```