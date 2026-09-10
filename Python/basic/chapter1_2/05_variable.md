## 변수

```python
a = [1, 2, 3]
# 객체의 주소값 반환
id(a)           # 2071517747200
b = a
id(b)           # 2071517747200
# 두 변수가 같은 객채를 가리키는지 확인
a is b          # True

# [:] 이용한 복사
b = a[:]
a[1] = 4
a               # [1, 4, 3]
b               # [1, 2, 3]

# copy 모듈 이용
from copy import copy
a = [1, 2, 3]
b = copy(a)
b is a          # False

# copy 함수
a = [1, 2, 3]
b = a.copy()    # 파이썬 리스트 내장 함수
b is a          # False
```

```python
# 튜플로 대입
a, b = ('python', 'life')
(a, b) = 'python', 'life'
a           # python
b           # life
a, b        # (python, life)
# 리스트
[a, b] = ['python', 'life']
a           # python
b           # life
a, b        # [python, life]
```

```python
a = b = 'python'

# 두 변수의 값 바꾸기
a = 3
b = 5
a, b = b, a
a           # 5
b           # 3
```
