### Format type 8bit binary

```python

a=bin(11) #0b1101

b=f'{a[2:}:0>8}' #b=00001101 -str

```
### print 문 관련

```python
#연속 출력
for i in range(3):
  print(i,end=" ") #줄 바꿈 없이 한 칸 뛰우고 출력

```

### Lis Comprehension  
[표현식 for 항목 1 in 반복 가능한 객체1 if 조건 1  
        for 항목 2 in 반복 가능한 객체2 if 조건 2  
        ...  
        항목 n in 반복 가능한 객체n if 조건 n]  

```python
# 구구단
result=[x*y for x in range(2,10)
... for y in range(1,10)]
```

### 매개변수(Parameter) vs 인수(Arguments)

```python
def add(a,b): # 함수의 입력을 이야기 할 때 Parameter라고 함
  return a+b

print(add(3,4)) #함수를 호출 할 때 전달하는 입력 값을 Arguments라고 함.
```
