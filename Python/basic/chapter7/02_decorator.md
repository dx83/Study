## 데코레이터

> decorator
- 기존 함수를 수정하지 않고, 앞뒤에 새로운 기능을 추가하는 함수
```python
import time

def elapsed(original_func):         # 함수를 인수로 받음
    def wrapper():
        start = time.time()
        result = original_func()    # 인수로 받은 함수 실행
        end = time.time()
        print("함수 수행 시간: %f초" % (end - start))
        return result
    return wrapper

def myfunc():
    print("함수가 실행됩니다.")

decorated_myfunc = elapsed(myfunc)
decorated_myfunc()
# 함수가 실행됩니다.
# 함수 수행 시간: 0.000243초
```
- 기존 함수를 바꾸지 않고 elapsed 함수와 같은 클로저를 데코레이터라고 한다.

<br>

> @함수명
```python
@elapsed
def myfunc():
    print("함수가 실행됩니다.")

# decorated_myfunc = elapsed(myfunc)
# decorated_myfunc()

myfunc()
# 함수가 실행됩니다.
# 함수 수행 시간: 0.000076초
```

<br>

> *args, **kwargs : 다양한 입력 인수 처리
- 인수로 받은 함수 실행시 *args, **kwargs를 해당 함수에 인수로 전달하여 호출
```python
import time

def elapsed(original_func):                         # 함수를 인수로 받음
    def wrapper(*args, **kwargs):                   # 매개변수 추가
        start = time.time()
        result = original_func(*args, **kwargs)     # 인수를 받아 함수 실행
        end = time.time()
        print("함수 수행 시간: %f초" % (end - start))
        return result
    return wrapper

@elapsed
def myfunc(msg):
    print("'%s'을 출력합니다." % msg)

myfunc("You need python")
# 'You need python'을 출력합니다.
# 함수 수행 시간: 0.000392초
```
