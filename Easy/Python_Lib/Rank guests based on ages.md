**Question:**

Rank guests based on their ages.
Output the guest id along with the corresponding rank.
Order records by the age in descending order.

-------------------------------------------------------------------
**Solution:**
```python
airbnb_guests['rank'] = airbnb_guests['age'].rank(
    method = 'min', ascending = False)
result = airbnb_guests[['guest_id','rank']].sort_values('rank')
```