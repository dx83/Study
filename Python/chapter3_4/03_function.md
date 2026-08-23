## 함수

- 매개변수 `parameter`
- 인수 `arguments`

```python
def add(a, b):      # a, b는 매개변수
    return a + b
print(add(3, 4))    # 3, 4는 인수

# 매개변수없는 함수
def say():
    return 'Hi'

# 반환값이 없는 함수
def add(a, b):
    print("%d, %d의 합은 %d입니다." % (a, b, a + b))

# 입력값도 반환값도 없는 함수
def say():
    print('Hi')
```

<br>

`매개변수 지정`
```python
def sub(a=7, b=4):
    return a - b
result = sub()      # 3

def sub(a, b=4):
    return a - b
result = sub(5)     # 1

def sub(a=7, b):    # 오류
```

<br>

`여러 개의 입력값을 받는 함수 만들기`
```python
def 함수명(*매개변수):

def add_many(*args):
    result = 0
    for i in args:
        result += i
    return result

result = add_many(1, 2, 3)                          # 6
result = add_many(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)    # 55

def add_mul(choice, *args):
    if choice == "add":
        result = 0
        for i in args:
            result += i
    elif choice == "mul":
        result = 1
        for i in args:
            result *= i
    return result

result = add_mul('add', 1, 2, 3, 4, 5)      # 15
result = add_mul('mul', 1, 2, 3, 4, 5)      # 120
```

<br>

`키워드 매개변수, kwargs`
```python

```