# 쿼리 파라미터 (query parameter)
> 경로 뒤 ? 다음에 'key=value' 형태로 붙어 클라이언트가 선택적으로 전달하는 데이터

```python
/items?max_price=1000
------ --------------
경로    쿼리 파라미터

# 값을 전달하지 않아도 None으로 처리
@app.get("/items")
def read_items_handler(max_price: int | None = None):
    return {"max_price": max_price}
```

- 경로 변수는 경로에서 값을 추출하고, 쿼리 파라미터는 경로의 ? 뒤에 붙은 값을 추출

<br>

# Pydantic
> 데이터 검증 라이브러리  
> 입력된 데이터가 올바른 형식인지 확인하는데 사용

```python
# BaseModel : FastAPI 에서 요청 본문이나 응답 본문을 구조화하고 검증
from pydantic import BaseModel
# 데이터를 검증하려면 BaseModel을 상속받아 Pydantic 모델 정의
class Item(BaseModel):
    name: str
    price: int
    in_stock: bool = True
# 지정된 타입과 구조를 따르는지 자동으로 검사
# 잘못된 값이 들어오면 ValidationError를 발생시켜 오류 확인 가능

data = {"name": "Laptop", "price": 1200, "in_stock": False}
new_item = Item(**data)     # 언패킹

data = {"name": 123, "price": "abc"}
new_item = Item(**data)     # ValidationError 발생
```
- 언패킹 (unpacking) : 딕셔너리나 리스트 같은 자료구조에 들어 있는 값을 변수나 함수 인자로 풀어서 전달
