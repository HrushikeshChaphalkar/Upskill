**Question:**

You are provided with a transactional dataset from Amazon that contains detailed information about sales across different products and marketplaces.
Your task is to list the top 3 sellers in each product category for January.

The output should contain 'seller_id' , 'total_sales' ,'product_category' , 'market_place', and 'month'.

-------------------------------------------------------------------
**Solution:**
```python
sales_data['month'] = sales_data['month'].astype(str)
january_sales = sales_data[sales_data['month'].str.startswith('2024-01')]

result = (
    january_sales.groupby('product_category', group_keys=False)
    .apply(lambda x: x.nlargest(3, 'total_sales'))
    .reset_index(drop=True)
    )
```