**Question:**

Find the total cost of each customer's orders. Output customer's id, first name, and the total order cost. Order records by customer's first name alphabetically.

---
**Solution:**
```python
import pandas as pd

merge = pd.merge(customers, orders, left_on ='id', right_on = 'cust_id')
result = (
    merge.groupby(['cust_id', 'first_name'])['total_order_cost']
    .sum()
    .reset_index()
    .sort_values('first_name', ascending = True)
    )
```