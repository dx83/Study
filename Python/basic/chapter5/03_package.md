## 패키지
`모듈의 집합`

> 패키지 안의 함수 실행하기
```python
# game 폴더 안의 sound 폴더안의 echo.py
import game.sound.echo
game.sound.echo.echo_test()     # echo 모듈안의 함수 실행

from game.sound import echo
echo.echo_test()

from game.sound.echo import echo_test
echo_test()
```
- 사전에 패키지의 path 를 맞춰야 함
    - (path 설정 또는 해당 디렉토리 위치에서 실행)

```python
# 다음 방식은 불가
import game
game.sound.echo.echo_test()

import game.sound.echo.echo_test
```

<br>

> `__init__.py`  
> 해당 디렉터리가 패키지의 일부임을 알려 주는 역할  
> 패키지와 관련된 설정이나 초기화 코드 포함 가능
```python
# 다른 모듈 미리 import 가능
from .graphic.render import render_test # 맨 앞의 .은 현재 디렉터리 의미

# 패키지 변수와 함수 정의
VERSION = 3.5
def print_version_info():
    print(f"The version of this game is {VERSION}.")

# 패키지 초기화 코드 작성
print("Initialiaing game ...")
```
- 패키지 초기화 코드 실행
```python
# 패키지를 처음 import 하거나
import game
# Initialiaing game ...

# game 패키지의 하위 모듈의 함수를 import 할 경우에도 실행
from game.graphic.render import render_test
# Initialiaing game ...
```
- 초기화 코드는 한번만 실행됨
```python
import game
from game.graphic.render import render_test
# Initialiaing game ...
```

<br>

> `__all__`  
> 모든 것(*)을 import 할 때 해당 디렉터리에 다음 정의
```python
# __init__.py
__all__ = ['echo']
```
```python
# sound 폴더 __init__.py 에 __all__ 정의
from game.sound import *
echo.echo_test()        # 오류 없음
```

<br>

> relative 패키지
```python
# game 패키지의 render.py 모듈에서 다른 디렉토리에 있는 모듈 사용
from game.sound.echo import echo_test   # 기본
from ..sound.echo import echo_test      # relative

def render_test():
    print("render")
    echo_test()
```
- .. : 부모 디렉터리
- . : 현재 디렉터리