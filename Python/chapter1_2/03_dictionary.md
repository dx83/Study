## 딕셔너리 자료형
`Key 와 Value를 한 쌍으로 가지는 자료형`

```python
{Key1: Value1, Key2: Value2, Key3: Value3, ...}

a = {'a': [1, 2, 3]}    # Value에 리스트 가능
```

```python
# 요소 쌍 추가
a = {1: 'a'}
a[2] = 'b'
# {1: 'a', 2: 'b'}
a['name'] = 'pey'
# {1: 'a', 2: 'b', 'name': 'pey'}
 a[3] = [1, 2, 3]
# {1: 'a', 2: 'b', 'name': 'pey', 3: [1, 2, 3]}

# 요소 삭제
del a[1]    # Key가 1인 Key:Value 쌍 삭제
# {2: 'b', 'name': 'pey', 3: [1, 2, 3]}
```

> 인덱스 번호 접근 불가  
> 슬라이싱 불가
> Key 값이 중복되면 하나를 제외하고 나머지 무시
> Key 값에 리스트 사용 불가

```python
# key 리스트 만들기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
a.keys()            # dict_keys 객체 반환, 반복문에서 키값 반환
# dict_keys(['name', 'phone', 'birth'])
b = list(a.keys())  # list 자료형으로 만들기
# ['name', 'phone', 'birth']

# value 리스트 만들기
a.values()          # dict_values 객체 반환
# key,value 쌍 얻기
a.items()           # dict_items 객체 반환
```

```python
# 딕셔너리 안의 모든 요소 삭제
a.clear()           # {} 반환

# key값으로 value 얻기
a.get('name')       # 'pey' 반환

# 존재하지 않는 키값
a['example']        # 오류 발생
a.get('example')    # None 반환
a.get('example', 'nokey')   # nokey 반환

# key가 딕셔너리 안에 있는지 조사
'name' in a         # True
'example' in a      # False
```

