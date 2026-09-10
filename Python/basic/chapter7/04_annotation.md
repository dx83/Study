## 타입 어노테이션

> type annotation
- 변수와 함수에 타입을 지정
```python
# num 변수가 int형 명시
num: int = 1

# add 함수가 int형 매개변수 a,b를 받아 int형을 반환
def add(a: int, b: int) -> int:
    return a + b
```

<br>

- 파이썬 타입 어노테이션은 체크가 아닌 힌트
```python
def add(a: int, b: int) -> int:
    return a + b

result = add(3, 3.4)
print(result)
```

<br>

> mypy
- 타입 검사기
```python
pip install mypy
```
- 타입이 틀리면 오류 발생 시킴
