# 1. 배열 만들기

. np.array - 배열 생성  
. np.zeros - 0이 들어있는 배열 생성  
. np.ones - 1이 들어있는 배열 생성  
. np.empty - 초기화가 없는 값으로 배열을 반환  
. np.arange(stop) - 배열 버전의 range 함수  
. np.random - 다양한 난수가 들어있는 배열 생성  
```python
a = np.random.randint(0, 5, (3, 5))
```

# 2.배열 기초
```python

    print("1차원 array")
    array = np.arange(10)
    print(array)

    # Q1. array의 자료형을 출력해보세요.
    print("자료형:", type(array))

    # Q2. array의 차원을 출력해보세요.
    print("차원:", array.ndim)

    # Q3. array의 모양을 출력해보세요.
    print("모양:", array.shape)

    # Q4. array의 크기를 출력해보세요.
    print("크기:", array.size)

    # Q5. array의 dtype(data type)을 출력해보세요.
    print("dtype:", array.dtype)


    print("2차원 array")
    matrix = np.arange(1, 16).reshape(3, 5)  # 1부터 15까지 들어있는 [3, 5]짜리 배열을 만듭니다.
    print(matrix)

    # Q1. matrix의 자료형을 출력해보세요.
    print("자료형:", type(matrix))

    # Q2. matrix의 차원을 출력해보세요.
    print("차원:", matrix.ndim)

    # Q3. matrix의 모양을 출력해보세요.
    print("모양:", matrix.shape)

    # Q4. matrix의 크기를 출력해보세요.
    print("크기:", matrix.size)

    # Q5. matrix의 dtype(data type)을 출력해보세요.
    print("dtype:", matrix.dtype)
```
