## 예외처리

> 오류 회피
```python
# 파일이 없더라도 오류가 나지 않고 통과
try:
    f = open("없는파일", 'r')
except FileNotFoundError:
    pass
```

<br>

> 일부러 오류 발생  
> raise 명령어
```python
# 자식 클래스 Eagle에서 fly 함수를 구현하도록 유도
class Bird:
    def fly(self):
        raise NotImplementedError

class Eagle(Bird):
    pass

eagle = Eagle()
eagle.fly()     # NotImplementedError
```

<br>

> 예외 만들기
```python
class MyError(Exception):
    def __str__(self):
        return "허용되지 않는 별명입니다."

def say_nick(nick):
    if nick == "바보":
        raise MyError()
    print(nick)

try:
    say_nick("천사")
    say_nick("바보")
#except MyError:
#    print("허용되지 않는 별명입니다.")
except MyError as e:    # __str__ 메서드 구현한 경우
    print(e)
```
