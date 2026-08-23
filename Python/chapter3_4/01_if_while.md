## 조건문
> 들여쓰기 : 다음 둘 중에 하나로 통일  
> - 공백 문자 4개  
> - 탭 문자

<br>

- x or y : x 와 y 둘 중 하나만 참이어도 참
- x and y : x 와 y 모두 참이어야 참
- not x : x가 거짓이면 참
```python
money = 2000
card = True
if money >= 3000 or card:
    print("택시를 타고 가라")
else:
    print("걸어라가")
# 택시를 타고 가라
```

<br>

- x in 리스트, 튜플, 문자열 : 해당 자료형 안에 x가 있으면 참
- x not in 리스트, 튜플, 문자열 : 해당 자료형 안에 x가 없으면 참
```python
1 in [1, 2, 3]          # True
4 not in [1, 2, 3]      # True
'd' in ('a', 'b', 'c')  # False
't' not in 'Python'     # False
``` 

## if, else, elif

## 조건부 표현식
```python
score = 85
message = "success" if score >= 60 else "failure"
message         # 'success'
```

## while, break, continue
```python
coffee = 10
while True:
    money = int(input("돈을 넣어 주세요: "))
    if money == 300:
        print("커피를 줍니다.")
        coffee -= 1
    elif money > 300:
        print("거스름돈 %d를 주고 커피를 줍니다." % (money - 300))
        coffee -= 1
    else:
        print("돈을 다시 돌려 주고 커피를 주지 않습니다.")
        print("남은 커피의 양은 %d개입니다." % coffee)
    if coffee == 0:
        print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
        break
```
