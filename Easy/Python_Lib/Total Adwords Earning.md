**Question:**

Find the total AdWords earnings for each business type. Output the business types along with the total earnings.

-------------------------------------------------------------------
**Solution:**
```python
result = (
    google_adwords_earnings[['business_type', 'adwords_earnings']]
    .groupby(['business_type'])
    .sum('adwords_earnings')
    .reset_index()
    )
```