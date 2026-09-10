## 함수

> 함수의 반환값은 언제나 하나
```python
def add_and_mul(a, b, c, d, e):
    return a + b, a - c, a * d, a / e

result = add_and_mul(10, 1, 2, 3, 5)    # tuple 로 반환
# (11, 8, 30, 2.0)

def add_and_sub(a, b):
    return a + b, a - b

result1, result2 = add_and_sub(3, 4)    # 값 분리
print(result1)      # 7
print(result2)      # -1
```

<br>

> 매개변수 초깃값 설정
```python
def sub(a=7, b=4):
    return a - b
result = sub()      # 3

def sub(a, b=4):
    return a - b
result = sub(5)     # 1

def sub(a=7, b):    # 오류

def sub(a, b=2, c=4):
    return a + b - c
result = sub(2)     # 0
```

<br>

> 매개변수를 지정하여 호출하기
```python
def assign(ace=5, big=3, center=0, dot=3): 
    return ace + big - center -dot

result = assign(dot=4,big=12)   # 13
```


<br>

> lambda 예약어  
> 함수를 한 줄로 간결하게 만들 수 있을 때 사용

`함수명 = lambda 매개변수1, 매개변수2, ... : 매개변수를 이용한 표현식`
```python
add = lambda a, b: a + b
result = add(3, 4)          # 7
```
