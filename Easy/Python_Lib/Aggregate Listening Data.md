**Question:**

You're tasked with analyzing a Spotify-like dataset that captures user listening habits.
For each user, calculate the total listening time and the count of unique songs they've listened to. In the database duration values are displayed in seconds. Round the total listening duration to the nearest whole minute.

The output should contain three columns: 'user_id', 'total_listen_duration', and 'unique_song_count'.

-------------------------------------------------------------------
**Solution:**
```python
import pandas as pd

listening_habits['listen_duration'].fillna(0, inplace = True)
result = (
    listening_habits.groupby(['user_id'])
    .agg(total_listen_duration = ('listen_duration', 'sum'), 
    unique_song_count = ('song_id', 'nunique'))
    .reset_index()
    )
result['total_listen_duration'] = (result['total_listen_duration']/60).round()
```