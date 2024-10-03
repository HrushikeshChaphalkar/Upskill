**Question:**

For each week, find the total number of orders. Include only the orders that are from the first quarter of 2023.

The output should contain 'week' and 'quantity'.

-------------------------------------------------------------------
**Solution:**
```python
import pandas as pd
orders_analysis['week'] = pd.to_datetime(orders_analysis['week'])
orders_analysis['quarter'] = orders_analysis['week'].dt.quarter
orders_analysis['year'] = orders_analysis['week'].dt.year
first_quarter_df = orders_analysis[(orders_analysis['quarter'] == 1) & (orders_analysis['year'] == 2023)]
result = first_quarter_df.groupby(['week'])['quantity'].sum().reset_index()
```