# POST API : 데이터 생성

`schema/request.py`
```python
from pydantic import BaseModel

# 할 일 생성 요청 모델
class TodoCreateRequest(BaseModel):
    title: str
    is_done: bool = False
```


`main.py`
```python
from schema.request import TodoCreateRequest # 추가

# 할 일 생성
@app.post(
    "/todos",
    response_model=TodoResponse,
    status_code=status.HTTP_201_CREATED
)
def create_todo_handler(body: TodoCreateRequest):
    new_todo = {
        "id": len(todos) + 1,
        "title": body.title,
        "is_done": body.is_done
    }
    todos.append(new_todo)
    return new_todo

# Swagger UI : 장보기, False
# Response body
{
  "id": 4,
  "title": "장보기",
  "is_done": false
}
```
