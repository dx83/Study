## 클로저

> closure
- 함수 안에서 만들어진 내부 함수가, 바깥 함수의 변수를 기억하고 사용하는 구조
```python
#----------------------------------------
class Mul:
    def __init__(self, m):
        self.m = m
    
    def mul(self, n):
        return self.m * n

if __name__ == '__main__':
    mul3 = Mul(3)       # mul함수 : 3 x n
    mul5 = Mul(5)       # mul함수 : 5 x n

    print(mul3.mul(10)) # 30
    print(mul5.mul(10)) # 50

#----------------------------------------
class Mul:
    def __init__(self, m):
        self.m = m
    
    # __call__
    # Mul 클래스로 만든 객체에 인수를 전달하여
    # 바로 호출할 수 있도록 하는 메서드
    def __call__(self, n):
        return self.m * n

if __name__ == "__main__":
    mul3 = Mul(3)
    mul5 = Mul(5)

    print(mul3(10))
    print(mul5(10))

#----------------------------------------
def mul(m):
    def wrapper(n):     # 함수의 안의 함수
        return m * n
    return wrapper

if __name__ == "__main__":
    mul3 = Mul(3)
    mul5 = Mul(5)

    print(mul3(10))
    print(mul5(10))
```
