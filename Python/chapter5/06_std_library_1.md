## 표준 라이브러리

> operator.itemgetter, operator.attrgetter
- itemgetter : 리스트/튜플/딕셔너리 같은 객체에서 특정 위치나 키의 값을 꺼내는 함수
- attrgetter : 클래스 객체에서 특정 위치나 키의 값을 꺼내는 함수
```python
from operator import itemgetter

students = [
    {"name": "jane", "age": 22, "grade": 'A'},
    {"name": "dave", "age": 32, "grade": 'B'},
    {"name": "sally", "age": 17, "grade": 'B'},
]

result = sorted(students, key=itemgetter('age')) # 나이순으로 정렬
# {'name': 'sally', 'age': 17, 'grade': 'B'}
# {'name': 'jane', 'age': 22, 'grade': 'A'}
# {'name': 'dave', 'age': 32, 'grade': 'B'}

from operator import attrgetter

class Student:
    def __init__(self, name, age, grade):
        self.name = name
        self.age = age
        self.grade = grade

students = [
    Student('jane', 22, 'A'),
    Student('dave', 32, 'B'),
    Student('sally', 17, 'B'),
]

result = sorted(students, key=attrgetter('age'))    # 나이순으로 정렬
for s in students:
    print(s.name,s.age,s.grade)
# jane 22 A
# dave 32 B
# sally 17 B
```

<br>

> shutil
- 파일 복사, 이동
```python
import shutil
shutil.copy("./test.txt", "./test.bak")         # a파일을 b형태로 복사 생성
shutil.move("./test.bak", "../00_0/test.bak")   # a파일을 b형태로 이동
```

<br>

> pickel
- 객체의 형태를 그대로 유지하면서 파일에 저장하고 불러올 수 있게 하는 모듈
```python
import pickle
f = open("test.pickle", 'wb')
data = {1: 'python', 2: 'you need'}
pickle.dump(data, f)    # 객체를 파일로 저장
f.close()

f = open("test.pickle", 'rb')
data = pickle.load(f)   # 저장한 파일 불러오기
print(data)
```
