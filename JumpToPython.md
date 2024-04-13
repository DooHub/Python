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
