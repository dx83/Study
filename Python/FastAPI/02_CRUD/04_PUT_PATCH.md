# PUT / PATCH API : 데이터 수정

> PUT (전체 수정) : 모든 필드 수정, 요청 본문의 데이터로 기존 데이터를 통째로 덮어씀  
> PATCH (부분 수정) : 일부 필드 수정, 요청 본문에 포함된 항목만 변경

<br>

`schema/request.py`
```python
# 할 일 수정 요청 모델
class TodoUpdateRequest(BaseModel):
    title: str | None = None        # 선택 필드
    is_done: bool | None = None     # 선택 필드
```
- 선택 필드 : 해당 필드가 있을 수도 있고, 없을 수도 있음을 의미
    - 오류로 처리하지 않고 해당 필드의 값을 None으로 설정

`main.py`
```python
from schema.request import TodoCreateRequest, TodoUpdateRequest # 추가

# 할 일 수정
@app.patch(
    "/todos/{todo_id}",
    response_model=TodoResponse,
    status_code=status.HTTP_200_OK
)
def update_todo_handler(todo_id: int, body: TodoUpdateRequest):
    for todo in todos:
        if todo["id"] == todo_id:
            if body.title is not None:
                todo["title"] = body.title
            if body.is_done is not None:
                todo["is_done"] = body.is_done
            return todo
    raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="Todo not found")
```
