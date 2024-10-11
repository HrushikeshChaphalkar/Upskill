**Question:**

Find the number of acquisitions that occurred in each quarter of each year.
Output the acquired quarter in YYYY-Qq format along with the number of acquisitions and order results by the quarters with the highest number of acquisitions first.

-------------------------------------------------------------------
**Solution:**
```python
crunchbase_acquisitions["quarter_year"] = (
    crunchbase_acquisitions["acquired_quarter"].dt.year.astype(str)
    + "-Q"
    + crunchbase_acquisitions["acquired_quarter"].dt.quarter.astype(str)
    )
result = (
    crunchbase_acquisitions.groupby("quarter_year")
    .size()
    .to_frame("size")
    .reset_index()
    .sort_values("size", ascending=False)
)
```