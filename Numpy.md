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
# 3. 함수 및 연산
## 1) concatenate 함수
concatenate() 함수로 두 배열과 붙이는 방향을 설정하여 하나의 배열로 만들 수 있습니다.  
열의 개수가 같은 array끼리는 세로(axis=0)로 붙일 수 있고, 행의 개수가 같은 array끼리는 가로(axis=1)로 붙일 수 있습니다.  
```python
    matrix1 = np.array([[0, 1, 2, 3], [4, 5, 6, 7]])
    matrix2 = np.array([[8, 9, 10, 11], [12, 13, 14, 15]])
    print(matrix1)
    print(matrix2)
    print("matrix1 shape:", matrix1.shape)
    print("matrix2 shape:", matrix2.shape, "\n")

    # Q1. concatenate() 함수로 아래와 같은
    # 배열을 만들어 m에 저장하세요.
    """
    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]
     [12 13 14 15]]
    """
    m = np.concatenate([matrix1,matrix2],axis=0)

    print(m, "\n")

    # Q2. concatenate() 함수로 아래와 같은
    # 배열을 만들어 n에 저장하세요.
    """
    [[ 0  1  2  3  8  9 10 11]
     [ 4  5  6  7 12 13 14 15]]
    """
    n = np.concatenate([matrix1,matrix2],axis=1)

    print(n)
```
## 2) Split()함수
np.split(나눌 배열, [인덱스들], axis)  
```python
    matrix = np.array([[0, 1, 2, 3], [4, 5, 6, 7], [8, 9, 10, 11], [12, 13, 14, 15]])
    print(matrix, "\n")

    # Q1. 아래와 같은 모양이 나오도록 배열을 나누고 result1에 저장하세요.
    """
    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]]

    [[12 13 14 15]]
    """
    result1 = np.split(matrix,[3],axis=0)

    print(result1[0], "\n")
    print(result1[1], "\n")

    # Q2. 아래와 같은 모양이 나오도록 배열을 나누고 result2에 저장하세요.
    """
    [[ 0]
     [ 4]
     [ 8]
     [12]]

    [[ 1  2]
     [ 5  6]
     [ 9 10]
     [13 14]]

    [[ 3]
     [ 7]
     [11]
     [15]]
    """

    result2 = np.split(matrix,[1,3],axis=1)

    print(result2[0], "\n")
    print(result2[1], "\n")
    print(result2[2], "\n")
```
## 3)집계함수
```python
    print(matrix)

    # Q1. sum 함수로 matrix의 총 합계를 구해 출력해보세요.
    print(np.sum(matrix))
    
    # Q2. sum 함수의 axis 매개변수로 각 열의 합을 구해 출력해보세요.
    print(np.sum(matrix,axis=0))
    # Q3. sum 함수의 axis 매개변수로 각 행의 합을 구해 출력해보세요.
    print(np.sum(matrix,axis=1))
    # Q4. max 함수로 matrix 중 최댓값을 구해 출력해보세요.
    print(np.max(matrix))
    # Q5. min 함수로 matrix 중 최솟값을 구해 출력해보세요.
    print(np.min(matrix))
    # Q6. mean 함수로 matrix의 평균값을 구해 출력해보세요.
    print(np.mean(matrix))
    # Q7. std 함수로 matrix의 표준편차를 구해 출력해보세요.
    print(np.std(matrix))
    
    print(np.min(matrix,axis=0))
```
