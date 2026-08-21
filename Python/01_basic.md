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


