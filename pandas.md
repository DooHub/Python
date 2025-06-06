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

    # "japan" 인덱스부터 "usa" 인덱스까지 출력해봅시다.
    print(country.loc["japan":"usa"])
    
    # 인덱스 0부터 1까지의 값들을 출력해봅시다.
    print(country.iloc[0:2])


    print(country)
```

# 3. DataFrame 정렬하기
```python
import numpy as np
import pandas as pd

df = pd.DataFrame(
        {
            "col1": [2, 1, 9, 8, 7, 4],
            "col2": ["A", "A", "B", np.nan, "D", "C"],
            "col3": [0, 1, 9, 4, 2, 3],
        }
    )
    print(df, "\n")

    # 정렬 코드 입력해보기
    # Q1. col1을 기준으로 오름차순으로 정렬하기.
    print(df.sort_values("col1",ascending=True))
    
    # Q2. col2를 기준으로 내림차순으로 정렬하기
    print(df.sort_values("col2",ascending=False))
    
    # Q3. col2를 기준으로 오름차순으로, col1를 기준으로 내림차순으로 정렬하기
    print(df.sort_values(["col2","col1"],ascending=[True,False]))



```

# 4. 함수로 데이터 처리 하기
apply() 를 이용하면 함수를 이용하여 데이터 프레임에 값을 적용할 수 있습니다. lambda도 사용 가능합니다.
```python

    import pandas as pd
    import numpy as np


    df = pd.DataFrame(np.arange(5), columns=["Num"])
    print(df, "\n")

    # 값을 받으면 제곱을 해서 돌려주는 함수
    def square(x):
        return x ** 2

    # apply로 칼럼에 함수 적용
    df["Square"]=df["Num"].apply(square)
    
    # 람다 표현식으로도 적용하기
    df["Square"]=df["Num"].apply(lambda x : x**2)
```
