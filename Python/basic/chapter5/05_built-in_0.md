## 내장함수

- abs(x) : x의 절대값 반환
- all(x) : 반복 가능한 데이터 x를 입력 받아 x의 요소가 모두 참일때 True
- any(x) : 반복 가능한 데이터 x를 입력 받아 x의 요소 중 하나라도 참이 있으면 True
- chr(i) : 유니코드에 해당하는 문자 반환
- ord(c) : 문자의 유니코드 숫자 값 반환
- hex(x) : 정수를 16진수 문자열로 반환
- id(object) : 객체를 입력받아 객체의 고유 주솟값 반환
- int(x) : 문자열 형태의 숫자나 소수점이 있는 숫자를 정수로 반환
```python
abs(-1.3)               # 1.2

all([1, 2, 3])          # True
all([1, 2, 3, 0])       # False
all([])                 # 빈 값, True

any([1, 2, 3, 0])       # True
any([0, ""])            # 둘 다 거짓
any([])                 # 빈 값, False

chr(97)                 # 'a'
ord('가')               # 44032
hex(234)                # '0xea'

a = 3
id(3)                   # 140720961266664
id(a)                   # 140720961266664
b = a
id(b)                   # 140720961266664
c = 3
id(c)                   # 140720961266664

int("3")                # 3
int(3.4)                # 3
int('11', 2)            # 2진수를 10진수로 3
int('1A', 16)           # 16진수를 10진수로 26
```

<br>

- enumerate : 순서가 있는 데이터를 입력받아 인덱스 값을 포함하는 enumerate 객체 반환
```python
ls = ['body', 'foo', 'bar']
for i, name in enumerate(ls):
    print(i, name)
# 0 body
# 1 foo
# 2 bar
```

<br>

- filter : 반복 가능한 데이터의 요소 순서대로 함수를 호출했을 때 반환값이 참인 것만 반환
```python
filter(함수, 반복가능한데이터)

def positive(x):
    return x > 0

print(list(filter(positive, [1, -3, 2, 0, -5, 6])))
list(filter(lambda x: x > 0, [1, -3, 2, 0, -5, 6]))
# [1, 2, 6]
```

<br>

- isinstance(object, class) : 입력받은 객체가 그 클래스의 인스턴스인지 판단
```python
class Person: pass

a = Person()
isinstance(a, Person)   # True
b = 3
isinstance(b, Person)   # False
```
