## 프로그램의 입출력

> sys 모듈 사용
```python
import sys

args = sys.argv[1:]
for i in args:
    print(i)
```
```bat
C:\Workspace>python sys1.py aaa bbb ccc
aaa
bbb
ccc
```
```python
import sys
args = sys.argv[1:]
for i in args:
    print(i.upper(), end=' ')
```
```bat
C:\Workspace>python sys2.py life is too short, you need python
LIFE IS TOO SHORT, YOU NEED PYTHON
```

