## for

```python
test_list = ['one', 'two', 'three']
for i in test_list:
    print(i)
# one   # two   # three

a = [(1, 2), (3, 4), (5, 6)]
for (first, last) in a:
    print(first + last)
# 3     (1 + 2)
# 7     (3 + 4)
# 11    (5 + 6)
```

```python
# range(시작 숫자, 끝 숫자), 끝 숫자는 미포함
a = range(10)       # 0부터 9까지
a = range(1, 11)    # 1부터 10까지

marks = [90, 25, 67, 45, 80]
for number in range(len(marks))
    if mark[number] < 60:
        continue
    print("%d번 학생 축하합니다. 합격입니다." % (number + 1))

# 구구단
for i in range(2, 10):
    for j in range(1, 10):
        print(i*j, end=" ")     # end 파라미터
    print('')
'''
2 4 6 8 10 12 14 16 18 
3 6 9 12 15 18 21 24 27 
4 8 12 16 20 24 28 32 36 
5 10 15 20 25 30 35 40 45 
6 12 18 24 30 36 42 48 54 
7 14 21 28 35 42 49 56 63 
8 16 24 32 40 48 56 64 72 
9 18 27 36 45 54 63 72 81
'''
```

### 리스트 컴프리헨션 (list comprehension)

```python
a = [1, 2, 3, 4]
result = [num*3 for num in a]
result      # [3, 6, 9, 12]

result = [num*3 for num in a if num%2 == 0]
result      # [6, 12]

# 구구단
result = [x*y for x in range(2, 10)
              for y in range(1, 10)]
'''
[2, 4, 6, 8, 10, 12, 14, 16, 18, 3, 6, 9, 12, 15, 18, 21, 24, 27, 4, 8, 12, 16, 20, 24, 28, 32, 36, 5, 10, 15, 20, 25, 30, 35, 40, 45, 6, 12, 18, 24, 30, 36, 42, 48, 54, 7, 14, 21, 28, 35, 42, 49, 56, 63, 8, 16, 24, 32, 40, 48, 56, 64, 72, 9, 18, 27, 36, 45, 54, 63, 72, 81]
'''
```
