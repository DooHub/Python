# 1. 클래스 이해하기(class)

클래스는 무엇인가?

무엇인가를 반복적으로 만들어 낼 수 있는 “틀”입니다. 그리고 클래스(틀) 를 통해서 만들어진 그 무엇인가는 객체(object) 라고 합니다.
하나의 클래스를 가지고 여러 개의 객체를 만들 수 있습니다. 만들어진 객체들은 서로 아무런 영향을 주지 않습니다. 예를 들면 붕어빵 틀이 클래스(class) 라면, 만들어진 붕어빵은 객체(object) 인 것입니다.

클래스는 무엇으로 이루어져 있는가?

### 1) 멤버: 클래스 또는 객체에서 변수와 같은 역할
### 2) 메서드: 클래스 또는 객체에서 함수와 같은 역할
```python
class MyClass:
    var = "클래스 멤버"

    def func(self):
        print("메서드")
```
객체는 어떻게 생성하는가?

위에서 선언된 클래스로 아래와 같이 객체를 생성할 수 있습니다.  
```python
# my_class의 객체를 생성하여 obj1에 저장
obj1 = MyClass()

# MyClass의 또다른 객체를 생성하여 obj2에 저장
obj2 = MyClass()

# MyClass의 객체 obj2의 클래스 멤버 var를 출력
print(obj2.var)

# MyClass의 객체 obj1의 메서드 func()을 실행
obj1.func()
```

# 2, 클래스 멤버와 인스턴스 멤버 이해하기
### 1) 클래스 멤버: 객체 간 서로 공유되는 변수  
### 2) 인스턴스 멤버: 객체별로 고유한 값을 저장하는 변수
```python
class KiaK3:
    brand = "기아"  # 클래스 멤버
    model = "K3"  # 클래스 멤버

    def owner(self, name):
        self.name = name  # 인스턴스 멤버
```
brand, model의 값은 KiaK3클래스를 통해서 생성되는 모든 객체가 공유하게 됩니다.  
반면 name이라는 변수는 객체마다 고유의 값을 가지게 됩니다.  
인스턴스 멤버는 메서드 안에 self.멤버 이름을 통해 선언할 수 있습니다. (특정 객체의 멤버이기 때문에 self.멤버 이름의 형식으로 선언하는 것입니다.)  
위 KiaK3 클래스를 생성하는 아래 코드 예시를 참고하세요.  
```python
car1 = KiaK3()
car2 = KiaK3()
car1.name = "하얀 토끼"
car2.name = "엘리스"

# "차 주인은 하얀 토끼"를 출력
print("차 주인은", car1.name)

# "브랜드/모델: 기아 K3"를 출력
print("브랜드/모델:", car1.brand, car1.model)

# "차 주인은 엘리스"를 출력
print("차 주인은", car2.name)

# "브랜드/모델: 기아 K3"를 출력
print("브랜드/모델:", car2.brand, car2.model)
```

# 3. 메서드 이해하기
메서드는 함수와 같은 역할을 합니다.  

### 메서드 선언 방법  
첫 번째 인자는 관례상 반드시 self여야 하며, 이는 클래스로 생성된 객체를 의미합니다.  

set_owner 메서드에 객체와 name을 인자로 전달  
인스턴스 멤버 owner에 입력받은 두 번째 인자name을 저장  
설정된 차 주인을 출력  

```python
class Car:
    def set_owner(self, name):
        self.owner = name
        print("차 주인:", name)
```
### 메서드 호출 방법
클래스 이름을 이용한 메서드를 호출: self인자 필요  
객체 이름을 이용한 메서드를 호출: self인자 생략  
```python
# Car 클래스의 객체를 생성하여 my_car에 저장
my_car = Car()

# 클래스 이름인 Car로 메서드 호출
Car.set_owner(my_car, "엘리스")

# 객체 이름인 my_car로 메서드 호출
my_car.set_owner("엘리스")
```
# 4. 생성자 이해하기
생성자는 객체가 생성될 때마다 자동으로 실행되는 메서드입니다. 생성자는 클래스 내에서 다음과 같이 정의합니다. 
일반적으로 생성자는 인스턴스 변수를 설정해 주는 등의 초기화 작업을 수행합니다. 
생성자는 self 외에 여러 개의 인자를 가질 수 있습니다. 다음은 이름과 나이를 인자로 받는 클래스 예시입니다.  
이 클래스의 객체는 다음과 같이 생성할 수 있습니다.
```python
def __init__(self):
    # 여기에 생성자에서 처리하고자 하는 내용을 넣습니다.



class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("길동", 20)
```
# 5. 소멸자 이해하기
소멸자는 객체가 메모리에서 제거될 때 자동으로 실행되는 메서드입니다. 소멸자는 클래스 내에서 다음과 같이 정의합니다.  
객체를 메모리에서 제거하려면 다음과 같이 입력합니다.  
생성자나 소멸자와 같이 앞뒤에 “__” 가 붙는 경우, 특별한 용도로 예약한 메서드 명이라고 생각하시면 됩니다.  
```python
class Person:
    (생략)
    def __del__(self):
        # 여기에 소멸자에서 처리하고자 하는 내용을 넣습니다.
# 클래스 Person의 객체를 만들어 person에 저장합니다.
person = Person()

# 객체 person을 제거합니다.
del person
```
# 6.  클래스 상속 이해하기
상속은 하나의 클래스가 다른 클래스의 멤버와 메서드를 그대로 물려받아 사용할 수 있는 개념을 말합니다. 
상속받는 클래스를 자식 클래스, 상속하는 클래스를 부모 클래스라 부릅니다.  
자식 클래스는 서브 클래스, 부모 클래스는 슈퍼 클래스라고도 부릅니다.  
상속하는 방법은 다음과 같습니다. 
자식 클래스는 여러 개의 부모 클래스로부터 상속받을 수 있습니다.  
만약 자식 클래스와 부모 클래스의 멤버 또는 메서드가 중복된다면, 자식 클래스의 요소를 우선시합니다.  
```python
class SubClass(SuperClass):

# 1. Add 클래스에서 두 개의 수를 받아 덧셈하여 반환하는 add 함수를 구현해 주세요.
class Add:
    def add(self, n1, n2):
        return n1+n2

# 2. Calculator 클래스가 Add 클래스를 상속받도록 하세요.
class Calculator(Add):
    def sub(self, n1, n2):
        return n1 - n2

obj = Calculator()
print(obj.sub(1, 2))
# 3. obj 객체를 사용하여, 정수 1과 2를 더하는 연산을 해보세요.
print(obj.add(1,2))
```
