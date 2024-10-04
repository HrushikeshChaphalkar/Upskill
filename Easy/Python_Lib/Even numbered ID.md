**Question:**

Find employees who started in June and have even-numbered employee IDs.

-------------------------------------------------------------------
**Solution:**
```python
original_cols = worker.columns.to_list()
worker['month'] = worker['joining_date'].dt.month

june_filter = worker['month']==6
even_id = worker['worker_id'] %2==0

worker[june_filter & even_id][original_cols]
```