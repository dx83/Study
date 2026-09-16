# 상태 코드 (status code)
> 클라이언트의 요청에 대해 서버가 어떤 결과를 반환했는지를 숫자와 메시지로 나타내는 규약

| 상태 코드 |  | 설명 |
| :--- | :--- | :--- |
| **200** | OK | 요청이 성공적으로 처리되었음 |
| **201** | CREATED | 새로운 데이터가 성공적으로 생성되었음 |
| **204** | NO CONTENT | 요청은 성공했지만, 응답 본문에 반환할 데이터가 없음 (보통 삭제 요청 시 응답으로 많이 활용) |
| **400** | BAD REQUEST | 잘못된 요청으로 서버가 처리할 수 없음 |
| **401** | UNAUTHORIZED | 인증이 필요하거나 인증에 실패했음 |
| **403** | FORBIDDEN | 권한이 없어 요청이 거부되었음 |
| **404** | NOT FOUND | 요청한 데이터를 찾을 수 없음 |
| **500** | INTERNAL SERVER ERROR | 서버 내부에서 오류가 발생했음 |

<br>

```python
# 새 아이템 등록
@app.post(
        "/items",
        response_model=Item,
        status_code=status.HTTP_201_CREATED     # 성공 시 반환 코드 지정
)
def create_item_handler(item: Item):
    return item
```

- HTTP_200_OK
- HTTP_201_CREATED
- HTTP_204_NO_CONTENT
- HTTP_400_BAD_REQUEST
- HTTP_401_UNAUTHORIZED
- HTTP_403_FORBIDDEN
- HTTP_404_NOT_FOUND
- HTTP_500_INTERNAL_SERVER_ERROR
