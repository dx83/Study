# Swagger UI
> FastAPI가 자동으로 생성하는 API 문서 및 테스트 도구  
> 각 API 엔트포인트에 대해 요청과 응답을 시각적으로 보여 주고 직접 테스트 가능

<br>

# 요청 본문 다루기
```python
# 경로 변수, 쿼리 파라미터, 요청 본문 혼합 사용
@app.post("/Items/{item_id}")
def update_item_handler(item_id: int, assignee: str, item: Item):
    return {
        "item_id": item_id,
        "assingee": assignee, # 담당자 또는 작업자
        "item": item
    }

# Swagger UI : 1, tony, pencil, 1000, true 입력
# Response body
{
  "item_id": 1,
  "assingee": "tony",
  "item": {
    "name": "pencil",
    "price": 1000,
    "in_stock": true
  }
}
```

<br>

# 응답 본문 다루기
```python
@app.post("/items", response_model=Item)
def create_item_handler(item: Item):
    return item

# Swagger UI : eraser, 500, true
# Response body
{
  "name": "eraser",
  "price": 500,
  "in_stock": true
}
```

<br>

#
```python
class OrderResponse(BaseModel):
    order_id: int
    pickup: bool | None = None

@app.get("/orders/{order_id}", response_model=OrderResponse)
def get_order_handler(order_id: int, pickup: bool | None = None):
    return {
        "order_id": order_id,
        "pickup": pickup
    }
# Swagger UI : 5, true
# Response body
{
  "order_id": 5,
  "pickup": true
}
```
