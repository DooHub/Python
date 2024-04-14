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
### 함수의 Return값은 하나 (여러개의 경우 tuple로 묶어서 보냄)

```python
def add_and_mul(a,b):
    return a+b,a*b,a/b

d=add_and_mul(3,4)
a,b,c=add_and_mul(3,4)
```
d=(7,12,0.75) -->tuple
a,b=7,12 -->int
c=0.75 -->float

### lambda을 이용 방법
표현 방법 --> lambda 매개변수 1, 매개변수 2 ... : 매개변수를 이용한 수식
```python
add=lambda a,b : a+b
```
### file - open/read 관련
```python
#write 경우, 줄바꿈을 위해서는 마지막에 개행 문자 삽입 \n
f=open('text.txt','a')
a=1
line=f'write line{a}\n'
f.write(line)
f.close()
#Read 관련
linedata=f.readline() #기행문자 기준으로  한줄씩 읽음. linedata tyep str
linesdata=f.readlines() #전체를 읽어 list로 구성 list단위는 개행문자 기준. linesdata tyep list
data=f.read() #전체를 읽어 str으로 저장함 개행문자도 포함 되어 있음.
#통상 사용 별도 close()함수 호출 안 하기 위해 with 사용
with open('text.txt','a') as f
  a=1
  line=f'write line{a}\n'
  f.write(line)
  data=f.read()
```
### Class에 대해
class내에 구현 된 함수를 부를 때는 통상 Method라고 부른다.  
Magic Method는 __이름__ 이렇게 양쪽에 underscore로 구성 된 것을 말한다.  
Magic Method, Special Method라고도 불림 파이썬이 내부적으로 구현된(빌트인) 메소드를 구현함

### 객체(Object)와 인스턴스(Instance)관계
Class로 만든 객체를 인스턴스라고도 한다.  
Cookie()라는 Class가 있다고 할 때,  
관계 위주로 설명 할 때 a=Cookie() 이면 a는 Cookie()클래스의 인스턴스 이다.  
자체만을 말 할 때 a=Cookie()이면 a는 객체이고, Cookie는 클래스 이다.

### Method Overriding이란
자식 클래스가 부모 클래스에 있는 메서드를 자식 클래스에 재 정의 할 경우-같은 이름.
```python
# Parent class
class Parent:
  def __init__(self):
    pass
  def div(self,a,b):
    return a/b
# Child class
class child(Parent):
  def div(self,a,b): # Zerodivision error방지 추가
    if b==0:
      return 0
    else:
      return a/b
```

### Module 사용 방법
실행 source나 python 경로상에 사용하고자 하는 Module 파일이 위치 혹은 접근 가능해야 한다.  
mod1이라는 모듈 내에 add와 sub 함수가 있는 경우  
1. import 모듈이름  
```python
import mod1
# 모둘이름을 포함하여 함수 호출
mod1.add() 
mod1.sub()
```
2. from 모듈이름 import 모듈 함수(모듈 내 있는 함수)  
```python
from mod1 import add,sub
# 함수이름 바로 사용하여 호출
add() 
sub()
```

3. 모듈 호출 시 모듈 내 특정 부분을 포함 시키지 않는 방법
```python
if __name__=='__main__':
  #module이 자체 실행 할 때 수행하는 내용만 표
```
### 예외 처리
문법  
try:  
 수행 구문  
except 발생 오류 as 오류메시지 변수 :  
 오류 발생 시 수행 할 구문  

 ```python
try:
  4/0
except : # error발생하면 무조건 실행
  print("error")
  4/0
except ZeroDivisionError as e: # 발생 된 eorr가 ZeroDivisionError이면 수행
  print(e) # 전달 받은 error 메시지를 출력
```
### Error 발생 시키기
rasie NotImplementedError 을 Error발생 시키기 위한 부분에 삽입한다.  
class에 사용 할 경우, overriding방법을 사용하여 해당 Method의 Error을 회피 할 수 있다.
```python
class Bird:
  def fly(self):
    raise NotImplementedError
### filter 함수
첫번째 인수로 함수 이름, 두 번째 인수로 반복 가능한 자료(통상 List)받아 두 번째 인수 중 첫번째 인수(함수)에 대입 할 경우 '참'인 값만 반환  
반환 된 값들이 있는 주소를 알려 주기 때문에 최종에는 List로 형 변환을 해야 한다.
```python
#code구현 without filter
def positive(l):
  result=[]
  for i in l:
    if i>0:
      result.append(i)
  return result
# filter 사용 경우 1
def filter_positive(x):
  return x>0:

a=[1,-3,3,4,-5]

print(positive(a))
print(list(filter(filter_positive,a)))

# filter 사용 경우 2 lambda이용
print(list(filter(lambda x:x>0,a)))
  
```
class Eagle(Bird):
  def fly(self):
    print("Overriding to avoid error")
```
