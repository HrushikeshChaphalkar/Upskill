**Question:**

Find the number of rows for each review score earned by 'Hotel Arena'.
Output the hotel name (which should be 'Hotel Arena'), review score along with the corresponding number of rows with that score for the specified hotel.

-------------------------------------------------------------------
**Solution:**
```python
hotel_arena = hotel_reviews[hotel_reviews['hotel_name']=='Hotel Arena']
result = (
    hotel_arena
    .groupby('reviewer_score')
    .size()
    .reset_index()
    )
result.rename(columns={0: 'n_reviews'}, inplace=True)
result['hotel_name'] = 'Hotel Arena'
```