# 1. Series Data
Series 데이터란 NumPy array가 보강된 형태의 Data와 index를 가지고 있는 pandas의 데이터 형식입니다.  
```python

import pandas as pd

series = pd.Series([1, 2, 3, 4], index=["a", "b", "c", "d"], name="Title")
print(series)
```
