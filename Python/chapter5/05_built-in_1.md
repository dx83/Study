## 내장함수

- len(s) : 요소의 전체 개수 반환
- list(iterable) : 반복 가능한 데이터를 입력받아 리스트로 만들어 반환
- map(f, iterable) : 입력 데이터의 각 요소에 함수를 적용한 결과 반환
- sorted(iterable) : 입력 데이터를 정렬한 후 그 결과를 리스트로 반환
    - 리스트 자료형의 sort 함수는 정렬된 결과를 반환하지 않는다.
- zip(*iterable) : 동일한 개수로 이루어진 데이터들을 묶어서 반환
```python
len("python")       # 6
len([1, 2, 3])      # 3

list("python")      # ['p', 'y', 't', 'h', 'o', 'n']
a = [1, 2, 3]       # [1, 2, 3]
b = list(a)         # 리스트 복사

def two_times(x):
    return x * 2

list(map(two_times, [1, 2, 3, 4]))
list(map(lambda a: a*2, [1, 2, 3, 4]))
# [2, 4, 6, 8]

sorted([3, 1, 2])   # [1, 2, 3]
sorted("zero")      # ['e', 'o', 'r', 'z']

list(zip([1, 2, 3], [4, 5, 6], [7, 8, 9]))
# [(1, 4, 7), (2, 5, 8), (3, 6, 9)]
list(zip("abc", "def"))
# [('a', 'd'), ('b', 'e'), ('c', 'f')]
```

<br>

- max(iterable) : 최댓값 반환
- min(iterable) : 최솟값 반환
- pow(x, y) : x를 y제곱한 결괏값 반환
- round : 반올림해 반환
- sum(iterable) : 입력 데이터의 합을 반환하는 함수
```python
max([1, 2, 3])      # 3
max("python")       # 유니코드 값이 가장 큰 문자 반환 'y'
pow(2, 4)           # 16
round(4.6)          # 5
round(5.678, 2)     # 5.68  소수점 2자리까지만 반올림하여 표시
sum([1, 2, 3])      # 6
```

<br>

- str(object) : 문자열 형태로 객체를 변환하여 반환
- type(object) : 입력값의 자료형이 무엇인지 알려주는 함수
```python
str(3)                  # '3'

type("abc")             # <class 'str'>
type([])                # <class 'list'>
type(open("test", 'w')) # _io.TextIOWrapper
```
