## 슬라이싱
- 리스트 자료형 참고

## 문자열 포매팅
```python
number = 10
day = "three"
"I ate %d apples. so I was sick for %s days." % (number, day)
# 'I ate 10 apples. so I was sick for three days.'

"Error is %d%%." % 98
# 'Error is 98%.'

"I ate {0} apples. so I was sick for {1} days.".format(number, day)
# 'I ate 10 apples. so I was sick for three days.'
"I ate {number} apples. so I was sick for {day} days.".format(number=10, day=3)
# 'I ate 10 apples. so I was sick for 3 days.'

y = 3.42134234
"{0:0.4f}".format(y)
# '3.4213'
```
- %d : 정수
- %s : 문자열, 어떤 형태의 값이든 문자열로 바꾸어 대입
- 포매팅 문자를 문자 그대로 사용하고 싶은 경우 : %%, {{, }} 처럼 2개를 연속해서 사용

#### f 문자열 포매팅
```python
name = '홍길동'
age = 30
 f'나의 이름은 {name}입니다. 나이는 {age}입니다.'
# '나의 이름은 홍길동입니다. 나이는 30입니다.'

# 딕셔너리
d = {'name':'홍길동', 'age':30}
f'나의 이름은 {d["name"]}입니다. 나이는 {d["age"]}입니다.'
#   '나의 이름은 홍길동입니다. 나이는 30입니다.'

f'{"hi":<10}'
'hi        '
f'{"hi":>10}'
'        hi'
f'{"hi":^10}'
'    hi    '
y = 3.42134234
f'{y:0.4f}'
'3.4213'
f'{y:10.4f}'
'    3.4213'
```

#### 문자열 내장 함수
```python
a = "문자열"
```

- a.find('찾는문자열') : 찾는 문자열 인덱스, 없으면 -1 반환
- a.index('찾는문자열') : 찾는 문자열 인덱스, 없으면 오류 발생
- a.upper(), a.lower()
- a.lstrip(), a.rstrip(), a.strip() : 왼쪽, 오른쪽, 양쪽 공백 지우기
- a.replace(바뀔문자열, 바꿀문자열)

<br>

- a.split() : 공백을 기준으로 문자열 나눔
- a.split('구분자') : 값을 구분자로 해서 문자열을 나눔
