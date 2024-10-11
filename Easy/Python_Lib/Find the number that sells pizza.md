**Question:**

Find the number of Yelp businesses that sell pizza.

-------------------------------------------------------------------
**Solution:**
```python
pizza = yelp_business[yelp_business['categories'].str.contains('pizza', case = False)]
result = len(pizza)
```