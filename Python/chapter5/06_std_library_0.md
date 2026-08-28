## 표준 라이브러리

> datetime.date
```python
import datetime
day1 = datetime.date(2021, 12, 14)
day2 = datetime.date(2023, 4, 5)
diff = day2 - day1      # 날짜 연산
diff.days               # 477
day1.weekday()          # 1 화요일
day1.isoweekday()       # 2 화요일
```
- weekday() : 0월, 1화, 2수, 3목, 4금, 5토, 6일
- isoweekday() : 1월, 2화, 3수, 4목, 5금, 6토, 7일

<br>

> time
- time.time() : UTC를 사용한 현재 시간 실수 형태로 반환, 1970년1월1일0시0분0초
- time.sleep() : 일정한 시간 간격을 두고 반복문 실행
```python
import time
time.time()             # 1787910992.5196767

for i in range(10):
    print(i)
    time.sleep(5)       # 5초 간격 0부터 9까자의 숫자 출력
```

<br>

> random
- random.random() : 0.0 이상 1.0 미만의 임의의 실수를 반환
- random.randint(a,b) : a 이상 b 이하의 임의의 정수를 반환
- random.choice() : 리스트, 튜플, 문자열 같은 시퀀스에서 요소 하나를 무작위로 선택
- random.sample() : 요소 중에서 중복 없이 원하는 개수만큼 무작위로 뽑는 함수
```python
import random
random.random()                     # 0.9023511443829165
random.randint(1, 10)               # 5

def random_pop(data):
    number = random.choice(data)    # 무작위로 하나 선택
    data.remove(number)
    return number

data = [1, 2, 3, 4, 5]
while data:
    print(random_pop(data))

data1 = [1, 2, 3, 4, 5]
data2 = random.sample(data, len(data)) # (데이터, 뽑을 원소의 개수)
# [3, 4, 5, 2, 1]
```
