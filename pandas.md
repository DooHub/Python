# 1. Series Data
Series 데이터란 NumPy array가 보강된 형태의 Data와 index를 가지고 있는 pandas의 데이터 형식입니다.  
시리즈 데이터를 더욱 간편하게 만들기 위해서 파이썬의 딕셔너리를 이용할 수 있습니다.  

```python

import pandas as pd

series = pd.Series([1, 2, 3, 4], index=["a", "b", "c", "d"], name="Title")
print(series)

population_dict = {"korea": 5180, "japan": 12718, "china": 141500, "usa": 32676}
print(population_dict, "\n")

population = pd.Series(population_dict,name="Population")
print(population)
```
