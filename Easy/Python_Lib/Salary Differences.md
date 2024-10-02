**Question:**

Write a query that calculates the difference between the highest salaries found in the marketing and engineering departments.

Output just the absolute difference in salaries.

---
**Solution:**
```python
import pandas as pd

merge = pd.merge(
    db_employee,
    db_dept,
    how = 'left',
    left_on = 'department_id',
    right_on = 'id'
    )
highest_engineering_salary = merge[merge["department"] == "engineering"]['salary'].max()
highest_marketing_salary = merge[merge["department"] == "marketing"]['salary'].max()


salary_difference = abs(highest_marketing_salary - highest_engineering_salary)


result = pd.DataFrame({
    'salary_difference': [salary_difference]
})
```