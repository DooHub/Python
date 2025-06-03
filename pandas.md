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
# 2. DataFrame
시리즈 데이터는 하나의 칼럼으로 이루어진 반면 데이터 프레임은 여러 개의 칼럼을 가질 수 있습니다.  
데이터 프레임은 여러 개의 Series 데이터를 묶어놓은 것으로 볼 수 있습니다. 데이터 프레임을 만들기 위해서는 pd.DataFrame() 함수를 이용합니다.  
```python
    population_dict = {"korea": 5180, "japan": 12718, "china": 141500, "usa": 32676}
    # population에 population_dict를 이용하여 시리즈 데이터를 만들어주세요.
    population = pd.Series(population_dict)
    print("GDP series data:")
    gdp_dict = {
        "korea": 169320000,
        "japan": 516700000,
        "china": 1409250000,
        "usa": 2041280000,
    }
    # gdp에 gdp_dict를 이용하여 시리즈 데이터를 만들어주세요.
    gdp = pd.Series(gdp_dict)

    # 2개의 시리즈 값이 들어간 데이터프레임을 생성합니다.
    print("Country DataFrame")
    country = pd.DataFrame({"population":population,"gdp":gdp})

    # DataFrame에 1인당 GDP를 구한 값을 추가 합니다.
    country["gdp_per_pop"]=country["gdp"]/country["population"]

    # china 값만 출력 합니다.
    print(country.loc["chilna"])
    print(country.iloc[2])


    print(country)
```
