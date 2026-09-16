# HTTP
> HyperText Transfer Protocol  
> 표준 통신 프로토콜

#### HTTP 메서드
- GET :  데이터 조회
- POST : 새 데이터 생성(추가)
- PUT : 데이터 전체 수정
- PATCH : 데이터 일부 수정
- DELETE : 데이터 삭제

#### JSON 형식
> 클라이언트와 서버가 데이터를 주고받을 때 많이 사용하는 데이터 형식

<br>

# 경로 다루기
> 서버의 기본 주소  
> http://127.0.0.1:8000/경로  
> 경로(path)는 클라이언트가 서버로 요청을 보내는 주소로 기본 주소 뒤에 붙는 주소를 말함

<br>

#### 데코레이터 (decorator)
> 함수를 감싸서 실행 흐름이나 동작을 확장하는 파이썬 문법  
> 데코레이터를 활용해 HTTP 요청과 파이썬 함수를 연결

```python
@app.HTTP_메서드("경로",추가옵션1,추가옵션2,...)
def 함수명(매개변수):
    ...
```
- def 함수명(매개변수): 해당 요청이 들어왔을 때 실행되는 함수로 경로 함수, 엔드포인트 함수라고 함

<br>

#### 경로 변수
- 정적 경로 (static path) : @app.get("/login")
- 동적 경로 (dynamic path) : @app.get("/users/{user.id}")
- 경로 변수 (path parameter) : 클라이언트가 요청할 때마다 달라질 수 있는 값, {user.id}
- 타입 검증
    - `def read_user_handler(user_id: int):`
    - 타입 힌트를 지정하면 자동으로 타입 검증, 타입이 다르면 해당 요청을 처리하지 않고 오류를 반환

<br>

#### 엔드포인트 (endpoint)
> 클라이언트가 서버에 요청을 보내기 위해 사용하는 일종의 출입구

```python
@app.get("/")                   # 엔드포인트
    ...

@app.get("/login")              # 엔드포인트
    ...

@app.get("/users/{user.id}")    # 엔드포인트
    ...
```
