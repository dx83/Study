## 모듈
`모듈 : 함수나 변수 또는 클래스를 모아 놓은 파이썬 파일`

```python
# mod1.py
def add(a, b):
    return a + b

def sub(a, b):
    return a - b

if __name__ == "__main__":  # 없으면 import 할때 아래 구문 실행
    print(add(1, 4))
    print(sub(4, 2))
```
- `if __name__ == "__main__":`
    - 직접 파일 실행시 True
    - import 하는 경우 `__name__` 에 모듈 이름이 저장

<br>

> 모듈 불러오기
```python
import 모듈명

import mod1
print(mod1.add(3, 4))   # 7
print(mod1.sub(4, 2))   # 2
```
```python
from 모듈명 import 모듈함수

from mod1 import add
add(3, 4)

from mod1 import add, sub
from mod1 import *
```
- 모듈의 변수, 함수, 클래스를 사용할 수 있다.
- 인터프리터, 다른 파일에서 불러올 수 있다.
