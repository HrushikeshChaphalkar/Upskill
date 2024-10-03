**Question:**
You are given a dataset from Amazon that tracks and aggregates user activity on their platform in certain time periods. For each device type, find the time period with the highest number of active users.

The output should contain 'user_count', 'time_period', and 'device_type', where 'time_period' is a concatenation of 'start_timestamp' and 'end_timestamp', like ; "start_timestamp to end_timestamp".

---
**Solution:**
```python
import pandas as pd

user_activity['start_timestamp'] = pd.to_datetime(user_activity['start_timestamp'])
user_activity['end_timestamp'] = pd.to_datetime(user_activity['end_timestamp'])

user_activity['time_period'] = (
    user_activity['start_timestamp'].dt.strftime('%Y-%m-%d %H:%M:%S')
    + ' to '
    + user_activity['end_timestamp'].dt.strftime('%Y-%m-%d %H:%M:%S')
    )

result = user_activity.groupby(['device_type']).apply(
    lambda x: x[x['user_count'] == x['user_count'].max()]
)
result[['user_count', 'time_period', 'device_type']]
```