## 클래스

> 클래스로 만든 객체를 '인스턴스'
```python
class FourCal:
    pass        # 아무것도 수행않는 문법
a = FourCal()
type(a)         # 객체 a의 타입은 FourCal 클래스
# __main__.FourCal
```

<br>

> 메서드  
> 첫 번째 매개변수 self 는 자신을 호출한 객체가 자동으로 전달
```python
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result

a = FourCal()
a.setdata(4, 2)     # self 에 a 객체 자신이 전달됨
FourCal.setdata(a, 4, 2)    # 잘 사용하는 방법은 아님

a = FourCal()
a.add()             # first, second 값없음, 오류 발생 !!!
```

<br>

> 생성자  
> 객체가 생성될 때 자동으로 호출되는 메서드
```python
class FourCal:
    def __init__(self, first, second):
        self.first = first
        self.second = second
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
    def div(self):
        result = self.first / self.second
        return result

a = FourCal()       # 오류 발생 !!!
a = FourCal(4, 2)
```

<br>

> 상속
> 기존 클래스가 라이브러리이거나 수정이 허용되지 않는 경우 사용
```python
class 클래스명(상속할 클래스명):

class MoreFourCal(FourCal):
    def pow(self):
        result = self.first ** self.second
        return result

b = MoreFourcal(4, 2)
b.add()     # 6
b.pow()     # 16
```

<br>

> 메서드 오버라이딩
> 부모 클래스에 있는 메서드를 동일한 이름으로 다시 만드는 것
```python
c = FourCal(4, 0)
c.div()     # 0으로 나눌 때 오류

class SafeFourCal(FourCal):
    def div(self):
        if self.second == 0:
            return 0
        else:
            return self.first / self.second

c = SafeFourCal(4, 0)
c.div()     # 0
```

<br>

> 클래스 변수
```python
클래스명.클래스변수

class Family:
    lastname = "김"

Family.lastname         # 김

a = Family()
a.lastname              # 김

Family.lastname = "이"
a.lastname              # 이

a.lastname = "박"       # lastname 객체변수 생성
Family.lastname = "이"

a.lastname              # 박
```
