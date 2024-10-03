**Question:**

Find doctors with the last name of 'Johnson' in the employee list. The output should contain both their first and last names.

---
**Solution:**
```python
last_name_filter = employee_list['last_name'] == 'Johnson'
profession_filter = employee_list['profession'] == 'Doctor'
result = employee_list[last_name_filter & profession_filter][['first_name', 'last_name']]
```