## 사용자 입출력

```python
a = input()
# 사용자가 키보드로 입력한 모든 것을 문자열로 저장

number = input("숫자를 입력하세요: ")
숫자를 입력하세요:  # 사용자 입력
type(number)
<class 'str'>
```

```python
for i in range(10):
    print(i, end=' ')   # 한 줄에 결괏값 출력하기
# 0 1 2 3 4 5 6 7 8 9
```

<br>

## 파일 읽고 쓰기

```python
파일객체 = open(파일이름, 파일열기모드)
f = open("newfile.txt", 'w')
f.close()

f1 = open("C:/Workspace/newfile1.txt", "w")     # 슬래시
f1.close()
f2 = open("C:\\Workspace\\newfile2.txt", "w")   # 역슬래시
f2.close()
f3 = open(r"C:\workspace\newfile3.txt", "w")    # raw string
f3.close()
```
- r : 파일을 읽기만 할 때 사용
- w : 파일에 내용을 쓸 때 사용
- a : 파일의 마지막에 새로운 내용을 추가할 때 사용

> write 함수
```python
f4 = open("c:/Workspace/newfile.txt", 'w')
for i in range(1, 11):
    data = "%d번째 줄입니다.\n" % i
    f.write(data)   # data를 파일 객체 f에 써라.
f.close()
```

> readline 함수
```python
# 한 줄 읽기
f5 = open("c:/Workspace/newfile.txt", 'r')
line = f.readline()
print(line)
f.close()
# 모든 줄 읽기
f6 = open("c:/Workspace/newfile.txt", 'r')
while True:
    line = f6.readline()
    if not line: break
    print(line)
f.close()
```
