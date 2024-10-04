**Question:**

Write a query to find which gender gives a higher average review score when writing reviews as guests. Use the `from_type` column to identify guest reviews. Output the gender and their average review score.

-------------------------------------------------------------------
**Solution:**
```python
import pandas as pd

merged = pd.merge(
    airbnb_reviews,
    airbnb_guests,
    left_on = 'from_user',
    right_on = 'guest_id'
    )
merged = merged[merged["from_type"] == "guest"]
group = (
    merged.groupby(['gender'])['review_score']
    .mean()
    .to_frame("avg_score")
    .reset_index()
    )
result = group[group['avg_score']== group['avg_score'].max()]
```