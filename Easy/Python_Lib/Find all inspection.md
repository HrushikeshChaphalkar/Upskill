**Question:**

Find all inspections which are part of an inactive program.

---
**Solution:**
```python
inactive_status_filter = los_angeles_restaurant_health_inspections['program_status']=='INACTIVE'
result = los_angeles_restaurant_health_inspections[inactive_status_filter]
```