# sqlalchemy 2.0

> docker를 사용한 db 연결
`database.py`
```python
from pydantic import Field
from sqlalchemy import create_engine
from sqlalchemy.orm import DeclarativeBase, sessionmaker

# 데이터베이스 연결 정보, compose.yaml
# DATABASE_URL = "mysql+pymysql://root:fastapi@localhost:3306/fastapi_db"

# 엔진 설정
engine = create_engine(
    Field(validation_alias="DATABSE_URL")
    echo=True,              # SQL 쿼리가 로그로 출력
    pool_pre_ping=True      # db 연결이 유효한지 실제 쿼리를 날려 사전에 확인
)

class Base(DeclarativeBase):
    pass

# 세션 팩토리 생성
SessionFactory = sessionmaker(
    # 세션이 사용할 데이터베이스 엔진 지정
    bind=engine,
    # 세션의 변경 내용을 자동으로 데이터베이스에 반영하지 않음
    autoflush=False,
    # 커밋 이후에도 세션에 있는 객체의 값을 유지
    expire_on_commit=False,
)

def get_db():
    with SessionFactory() as db:
        yield db
```

> DB 테이블 생성
`main.py`
```python
~~~ 중략 ~~~
from database import engine, Base

# DB 테이블 생성
Base.metadata.create_all(bind=engine)
~~~ 중략 ~~~
```
