# DELETE API : 데이터 삭제

`main.py`
```python
# 할 일 삭제
@app.delete(
    "/todos/{todo_id}",
    status_code=status.HTTP_204_NO_CONTENT
)
def delete_todo_handler(todo_id: int):
    for todo in todos:
        if todo["id"] == todo_id:
            todos.remove(todo)
            return
    raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail="Todo not found")
```
- DELETE /todos/{todo_id} 요청이 성공적으로 처리되었을 때 응답 본문은 비어있음
    - 서버가 요청을 정상적으로 처리했지만 반환할 자원이 없기 때문이다.
    - 상태 코드 204 NO CONTENT로 지정 : 반환할 내용이 없음을 의미
