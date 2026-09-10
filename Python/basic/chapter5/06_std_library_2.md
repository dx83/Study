## 표준 라이브러리

> OS
- 환경 변수나 디렉터리, 파일 등의 OS 자원을 제어할 수 있게 해 주는 모듈

<br>

> zipfile
- 여러 개의 파일을 zip 형식으로 압축하거나 해제할 때 사용하는 모듈

<br>

> json
- JSON 데이터를 쉽게 처리하고자 사용하는 모듈 
- load(), loads(), dump(), dumps()
```python
import json
with open('myinfo.json') as f:
    data = json.load(f)         # json 파일 읽기
# 딕셔너리 자료형으로 반환

data = {'name': '홍길동', 'birth': '0525', 'age': 30}
with open('myinfo1.json', 'w') as f:
    json.dump(data, f)          # json 파일 만들기

json_data = json.dumps(data)    # json 문자열 만들기
# '{"name": "\\ud64d\\uae38\\ub3d9", "birth": "0525", "age": 30}'
# 데이터를 아스크 형태로 저장

json.loads(json_data)           # json 문자열 딕셔너리로 역변환
# {'name': '홍길동', 'birth': '0525', 'age': 30}

json_dict = json.dumps(data, ensure_ascii=False) # 아스키 형태 방지
# '{"name": "홍길동", "birth": "0525", "age": 30}'
```
