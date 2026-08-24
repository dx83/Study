## 파일 읽고 쓰기

> readlines 함수
```python
# 파일의 모든 줄을 읽어서 각각의 줄을 요소로 가지는 리스트 반환
f = open("c:/workspace/newfiles.txt", 'r')
lines = f.readlines()
for line in lines:
    line = line.strip() # 줄 끝의 줄 바꿈 문자를 제거
    print(line)
f.close()
```

<br>

> read 함수
```python
# 파일의 내용 전체를 문자열로 반환
f1 = open("c:/workspace/newfile.txt", 'r')
data = f1.read()
print(data)
f.close
```

<br>

> 파일에 새로운 내용 추가하기, 추가 모드 ('a')
> 쓰기 모드('w')로 파일을 열 때 이미 존재하는 파일을 열면 그 파일의 내용이 모두 사라짐
```python
f2 = open("c:/workspace/newfile.txt", 'a')
for i in range(11, 20):
    data = "%d번째 줄입니다.\n" % i
    f2.write(data)
f2.close()
```

<br>

> with 문
```python
with open("c:/workspace/newfile.txt", 'w') as f3:
    f3.write("Life is too short, you need python")

with (
    open("a.txt", 'w') as f1,
    open("b.txt", 'w') as f2,
    open("c.txt", 'w') as f3,
    open("d.txt", 'w') as f4,
):
    f1.write("Life is ")
    f2.write("        too short,")
    f3.write("                   you need python")
    f4.write("Life is too short, you need python")
```
- with 문을 사용하면 with 블록을 벗어나는 순간, 열린 파일 객체가 자동으로 닫힌다.
