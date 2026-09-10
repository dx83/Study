## 파이썬과 유니코드

> unicode
- 전 세계의 문자와 기호에 각각 고유한 번호를 부여한 문자 표준
```python
# 파일에 적거나 다른 시스템으로 전송하려면 바이트 문자열로 변환해야 함
a = "Life is too short"
s = a.encode('utf-8')       # 바이트 문자열로 변환
# b'Life is too short'
type(s)
# bytes
```

> 인코딩
```python
# 여러 인코딩 방식
a = "한글"
s = a.encode('euc-kr')
# b'\xc7\xd1\xb1\xdb'

s = a.encode('utf-8')
# b'\xed\x95\x9c\xea\xb8\x80'
```

> 디코딩
```python
a = "한글"
s = a.encode('euc-kr')
s = s.decode('euc-kr')
# '한글'

a = "한글"
s = a.encode('euc-kr')
s = s.decode('utf-8')       # 오류 발생
# UnicodeDecodeError
```

<br>

> 입출력과 인코딩
```python
# 0. euc-kr로 작성된 파일 만들기
text = "안녕하세요. EUC-KR 테스트입니다."
with open('euc_kr.txt', 'w', encoding='euc-kr') as f:
    f.write(text)

# 1. euc-kr로 작성된 파일 읽기
with open('euc_kr.txt', encoding='euc-kr') as f:
    data = f.read()             # 유니코드 문자열

# 2. unicode 문자열로 프로그램 수행하기
data = data + "\n" + "추가 문자열"

# 3. euc-kr로 수정된 문자열 저장하기
with open('euc_kr.txt', encoding='euc-kr', mode='w') as f:
    f.write(data)

data
# 안녕하세요. EUC-KR 테스트입니다.
# 추가 문자열
```

<br>

> 소스 코드의 인코딩
- 파이썬 3.0부터 utf-8이 기본값
```python
# -*- coding: utf-8 -*-
```
- 이전 버전에서는 한글같은 비 ASCII 문자를 소스 코드에 직접 쓰려면  
파일 첫 줄에 작성 필요
