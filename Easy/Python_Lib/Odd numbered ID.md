**Question:**

Find employees who started in February and have odd-numbered employee IDs.

-------------------------------------------------------------------
**Solution:**
```python
original_cols = worker.columns.to_list()
worker['month'] = worker['joining_date'].dt.month

feb_filter = worker['month']==2
odd_id = worker['worker_id'] %2==1

worker[feb_filter & odd_id][original_cols]
```