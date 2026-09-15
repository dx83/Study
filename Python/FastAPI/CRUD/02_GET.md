# GET API : 전체 데이터 조회

`schema/response.py`
```python
from pydantic import BaseModel

# 할 일 응답 모델
class TodoResponse(BaseModel):
    id: int
    title: str
    is_done: bool
```

`main.py`
```python
from schema.response import TodoResponse
from fastapi import FastAPI, status

# 전체 할 일 조회
@app.get(
    "/todos",
    response_model=list[TodoResponse],
    status_code=status.HTTP_200_OK
)
def get_todos_handler():
    return todos
```

# GET API : 단일 데이터 조회

`main.py`
```python
from fastapi import FastAPI, status, HTTPException  # 예외 처리
# 단일 할 일 조회
@app.get(
    "/todos/{todo_id}",
    response_model=TodoResponse,
    status_code=status.HTTP_200_OK
)
def get_todo_handler(todo_id: int):     # 전체 조회와 함수 이름 다름 !!!
    for todo in todos:
        if todo["id"] == todo_id:
            return todo
    raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="Todo not found")     # 존재하지 않는 todo_id 를 요청하면, 예외 처리
```
