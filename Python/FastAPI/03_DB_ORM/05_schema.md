# pydantic을 이용한 schema
`schema.py`

```python
from pydantic import BaseModel, ConfigDict

# 요청용 공통 부모 모델
class StrictRequest(BaseModel):
    model_config = ConfigDict(
        extra="forbid",             # 선언하지 않은 필드가 들어오면 오류 일으킴
        str_strip_whitespace=True   # 모든 문자열 앞뒤 공백 자동으로 제거
    )

# 응답용 공통 부모 모델
class OrmResponse(BaseModel):
    # 데이터베이스 ORM 객체의 속성을
    # Pydantic 스키마가 객체 형태로
    # 바로 읽어서 변환할 수 있게 해주는 설정
    model_config = ConfigDict(from_attributes=True)



# 할 일 생성 요청 모델
class TodoCreateRequest(StrictRequest):
    title: str
    is_done: bool = False

# 할 일 수정 요청 모델
class TodoUpdateRequest(StrictRequest):
    title: str | None = None
    is_done: bool | None = None



# 할 일 응답 모델
class TodoResponse(OrmResponse):
    id: int
    title: str
    is_done: bool
```
