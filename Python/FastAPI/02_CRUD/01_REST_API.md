# REST API
> API : 요청과 응답의 규칙을 정의  

> C (Create) : 데이터 생성, POST  
> R (Read) : 데이터 조회, GET  
> U (Update) : 데이터 수정, PUT, PATCH  
> D (Delete) : 데이터 삭제, DELETE  

> REST API (Representational State Transfer API)  
> 웹상의 자원을 '경로'로 표현하고, 해당 자원에 대해 수행할 수 있는 동작을 HTTP 메서드로 정의하는 API 설계 방식

<br>

#### REST API 설계 원칙
- 자원은 명사로 표현하고, CRUD 동작은 HTTP 메서드로 구분

```python
POST /todos         # 할 일 생성
GET /todos          # 전체 할 일 조회
PUT /todos/{id}     # 특정 할 일 수정
DELETE /todos{id}   # 특정 할 일 삭제
```

```python
# 다음처럼 하면 역할 구분이 흐려짐
POST /createTodos           # 할 일 생성
GET /getTodos               # 전체 할 일 조회
PUT /updateTodosItem        # 특정 할 일 수정
DELETE /deleteTodosItem     # 특정 할 일 삭제
```
