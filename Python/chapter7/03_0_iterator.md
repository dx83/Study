## 이터레이터

> iterator
- iterable : 반복 가능 객체
- 반복 가능하다고 이터레이터는 아님
> iter()
```python
a = [1, 2, 3]
next(a)
# TypeError: 'list' object is not an iterator

ia = iter(a)
type(ia)        # ia = iter(a)

next(ia)        # 1
next(ia)        # 2
next(ia)        # 3
next(ia)        # StopIteration 예외 발생
```
```python
a = [1, 2, 3]
ia = iter(a)
for i in ia:
    print(i)
# 1
# 2
# 3
for i in ia:
    print(i)    # 값이 출력되지 않는다.
```
- for문이나 next로 그 값을 한 번 읽으면 그 값을 다시는 읽을 수 없다.

<br>

> 클래스로 이터레이터 만들기
```python
class MyIterator:
    def __init__(self, data):
        self.data = data
        self.position = 0

    def __iter__(self):                         # 반복 가능한 객체가 됨
        return self
    # __iter__ 메서드를 구현할 경우 반드시 __next__ 함수를 구현해야 함
    def __next__(self):                         # 반복 가능한 객체의 값을 차례대로 반환
        if self.position >= len(self.data):
            raise StopIteration
        result = self.data[self.position]
        self.position += 1
        return result

if __name__ == "__main__":
    i = MyIterator([1, 2, 3])
    for item in i:
        print(item)
# 1
# 2
# 3

class ReverseIterator:
    def __init__(self, data):
        self.data = data
        self.position = len(self.data) - 1

    def __iter__(self):
        return self

    def __next__(self):
        if self.position < 0:
            raise StopIteration
        result = self.data[self.position]
        self.position -= 1
        return result

if __name__ == "__main__":
    i = ReverseIterator([1, 2, 3])
    for item in i:
        print(item)
# 3
# 2
# 1
```
