## 예외처리

> try-except 문
```python
try:
except:

try:    
except 발생오류:

try:
except 발생오류 as 오류변수:

try:
    4 / 0
except ZeroDivisionError as e:
    print(e)
# division by zero
```

<br>

> try-finally 문  
> 사용한 리소스를 close 해야 할 때 많이 사용
```python
try:
    f = open('foo.txt', 'w')
    4 / 0       # ZeroDivisionError
finally:
    f.close()   # 중간에 오류가 나더라도 무조건 실행
```

<br>

> try-else 문  
> 오류가 발생하면 except 절, 발생하지 않으면 else 절 수행
```python
try:
    age = int(input('나이를 입력하세요: '))
except:
    print('입력이 정확하지 않습니다.')  # 숫자가 아닌 다른 값 입력
else:
    if age <= 18:
        print('미성년자는 출입금지입니다.')
    else:
        print('환영합니다.')
```

<br>

> 여러개의 오류 처리
> 제일 처음 만난 오류만 예외처리
```python
try:
    a = [1, 2]
    print(a[3])
    4 / 0
except ZeroDivisionError as e:
    print(e)
except (IndexError, FileNotFoundError) as e:    # IndexError 만 처리
    print(e)
finally:                                        # 항상 실행
    print("항상 실행합니다.")
# list index out of range
# 항상 실행합니다.
```
