## 제너레이터

> generator
- 이터레이터를 생성해 주는 함수
> yield
```python
def mygen():
    yield 'a'
    yield 'b'
    yield 'c'

g = mygen()
type(g)             # 'generator'

next(g)             # 'a'
next(g)             # 'b'
next(g)             # 'c'
next(g)             # StopIteration 예외 발생
```

<br>

> 제너레이터 표현식
```python
def mygen():
    for i in range(1, 1000):
        result = i * i
        yield result

gen = mygen()

print(next(gen))    # 1
print(next(gen))    # 4
print(next(gen))    # 9

# 제너레이터 표현식 (리스트 컴프리헨션 과 비슷, 리스트 대신 튜플 이용)
gen = (i * i for i in range(1, 1000))

print(next(gen))    # 1
print(next(gen))    # 4
print(next(gen))    # 9
```
