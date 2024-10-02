Question:

Find the gender that has made the most number of doctor appointments.
Output the gender along with the corresponding number of appointments.

-------------------------------------------------------------------
**Solution:**
```python
import pandas as pd
import numpy as np

result = (
    medical_appointments.groupby(['gender'])
    .size().to_frame("total")
    .reset_index()
    .sort_values('total', ascending=False).head(1)
    )
```