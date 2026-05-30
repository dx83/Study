## 학습 모델
```python
# 학습 모델 임포트
import sklearn.~~~
```
- ~ = 모델클래스() : 사용할 모델 객체 생성
- ~.fit(문제, 정답) : 주어진 데이터로 알고리즘 훈련
- ~.score(문제, 정답) : 정확도
- ~.predict([[a,b]]) : 원하는 수치를 넣어 해당값의 예측값 확인

<br>

## column_stack(tuple)
- 전달 받은 리스트를 일렬로 세운 다음 나란히 연결 (2차원 배열로 바꿔줌)
```python
import numpy as np
np.column_stack(([1,2,3],[4,5,6]))
```
```
array([[1,4],[2,5],[3,6]])
```

<br>

## 데이터를 8:2로 나누기
- x : 문제 데이터, 2차원 배열만 입력 가능 (어떤 컬럼의 몇번째 행인지 알아야함)
- y : 정답 데이터, 1 / 2차원 둘다 입력 가능 (3개 이상의 정답은 인식 못함)
```python
from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(x, y, train_size=0.8, random_state=123)

# 문제 데이터가 1차원 배열인 경우 2차원 배열로 바꿔야함
x_train = x_train.reshape(-1, 1)    # -1은 행 개수는 자동 계산하라는 뜻
x_test = x_test.reshape(-1, 1)

x_train.shape, x_test.shape, y_train.shape, y_test.shape
```
<br>
