**Question**
Find the total number of records that belong to each variety in the dataset.
Output the variety along with the corresponding number of records. Order records by the variety in ascending order.

---

**Solution**
```python
import pandas as pd
result = (
    iris.groupby(['variety'])['sepal_length'].count()
    .reset_index()
    .sort_values(by = 'variety')
)
```