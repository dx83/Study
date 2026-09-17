# ORM 모델 정의

> 파이썬 클래스로 작성, 하나의 클래스는 하나의 테이블과 대응  
> 모든 ORM 모델은 기준 클래스인 Base 클래스 상속 필수

```python
from sqlalchemy.orm import DeclarativeBase
class Base(DeclarativeBase):
    pass
# 2.0 이후에는 Base 클래스를 만든 후,
# 모델에서 이 Base 클래스를 상속받도록 함
```

```python
from sqlalchemy.orm import Mapped, mapped_column
```
- Mapped : ORM에 관리되는 칼럼임을 나타내는 타입 힌트
- mapped_column : 파이썬 클래스의 속성을 데이터베이스 칼럼으로 연결

<br>

```python
is_done: Mapped[bool] = mapped_column(
        Boolean,
        nullable=False,
        default=False               # 파이썬에서 처리
)
created_at: Mapped[datetime] = mapped_column(
        DateTime(timezone=True),
        nullable=False,
        server_default=func.now()   # db에서 처리
)
```

| 구분 | `default` | `server_default` |
| :--- | :--- | :--- |
| **처리 위치** | 파이썬 (SQLAlchemy 앱) | 데이터베이스 (DBMS) |
| **적용 시점** | 객체를 생성하고 INSERT 쿼리를 만들기 **전** | DB에 INSERT 쿼리가 실행되는 **순간** |
| **주요 용도** | 파이썬 함수(`uuid`, 커스텀 로직) 처리 | DB 내장 함수(`CURRENT_TIMESTAMP`, 고정값) 처리 |
| **장점** | DB 종류와 상관없이 일관된 로직 적용 가능 | 다중 서버 환경에서 DB 시간 기준 통일, DB 부하 분산 |
