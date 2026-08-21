## 슬라이싱
```python
a[0:4]    # 0번째 문자열부터 4자리
a[19:]    # 19번째 문자열부터 문자열 끝까지
a[:17]    # 문자열 처음부터 17번째 문자열까지
a[:]      # 문자열의 처음부터 끝까지
```

## 문자열 포매팅
```python
number = 10
day = "three"
"I ate %d apples. so I was sick for %s days." % (number, day)
# 'I ate 10 apples. so I was sick for three days.'

"Error is %d%%." % 98
# 'Error is 98%.'
```
%d : 정수
%s : 문자열

