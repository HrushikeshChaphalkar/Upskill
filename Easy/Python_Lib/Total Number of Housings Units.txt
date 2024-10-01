Question:
Find the total number of housing units completed for each year. Output the year along with the total number of housings. 
Order the result by year in ascending order.

Note: Number of housing units in thousands.
---------------------------------------------------------
Solution:

import pandas as pd

result = housing_units_completed_us.groupby(['year']).sum().reset_index()
result['total'] = result['south'] + result['west'] + result['midwest'] + result['northeast']
sorted_result = result.sort_values('year')
sorted_result[['year', 'total']]

---------------------------------------------------------
Correct Solution:

import pandas as pd

result = (
    housing_units_completed_us.groupby("year")[
        "south", "west", "midwest", "northeast"
    ]
    .sum()
    .reset_index()
)

result["total"] = (
    result["south"]
    + result["west"]
    + result["midwest"]
    + result["northeast"]
)
result = result[["year", "total"]].sort_values("year")