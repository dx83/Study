## SSH 원격 접속
> 프라이빗 키와 퍼블릭 키를 사용해 현재 사용하고 있는 기기를 깃허브에 인증하는 방식

### SSH 키 생성하기
▼ `ssh-keygen`
```c#
$ ssh-keygen
Generating public/private ed25519 key pair.
Enter file in which to save the key (/c/Users/dx83/.ssh/id_ed25519):             // 그냥 Enter
Created directory '/c/Users/dx83/.ssh'.
Enter passphrase for "/c/Users/dx83/.ssh/id_ed25519" (empty for no passphrase):  // 그냥 Enter
Enter same passphrase again:                                                     // 그냥 Enter
Your identification has been saved in /c/Users/dx83/.ssh/id_ed25519              // 프라이빗 키 경로
Your public key has been saved in /c/Users/dx83/.ssh/id_ed25519.pub              // 퍼블릭 키 경로
The key fingerprint is:
SHA256:4/H/Bfq7h1zjY5YudIjfVq9FVb8pzvZS7b97B2wX3F0 dx83@BOOK-V248ESO4O2
The key's randomart image is:
+--[ED25519 256]--+
|                .|
|                E|
|              . *|
|               o*|
|        S   .ooo+|
|       . + .o+=*=|
|        . . +*=*B|
|           ..=+@*|
|            ..&XO|
+----[SHA256]-----+

$ cd ~/.ssh
$ ls -al
total 10
drwxr-xr-x 1 dx83 197609   0 12월 31 21:11 ./
drwxr-xr-x 1 dx83 197609   0 12월 31 21:10 ../
-rw-r--r-- 1 dx83 197609 411 12월 31 21:11 id_ed25519        // 프라이빗 키
-rw-r--r-- 1 dx83 197609 102 12월 31 21:11 id_ed25519.pub    // 퍼블릭 키
```

<br>

### 깃허브에 퍼블릭 키 전송하기
> 사용자 컴퓨터에 있는 프라이빗 키와 깃허브 서버에 있는 퍼블릭 키를 비교<br>
> 두개의 키가 서로 맞으면 사용자 컴퓨터와 킷허브 저장소가 연결됩니다.

▼ 퍼블릭 키안의 내용 전체를 복사
```c#
$ cd ~/.ssh
$ cat id_ed25519.pub
ssh-ed25519 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```
- 깃허브 웹브라우저
  - 사용자 아이콘 클릭
  - Settings 선택
  - SSH and GPG keys 선택
  - New SSH key 선택
  - key 항목에 퍼블릭 키 내용 복사
    - Add SSH key 클릭

<br>

### SSH 주소로 원격 저장소 연결하기
- 저장소 페이지
  - <> Code 클릭
  - Local 탭
    - SSH 항목에 있는 주소 복사
```c#
$ git init connect-ssh
$ git remote add origin SSH 주소

$ git remote -v
origin  SSH 주소 (fetch)
origin  SSH 주소 (push)

$ vim f1.txt
$ git add f1.txt
$ git commit -m "add f1"

$ git push origin master
The authenticity of host 'github.com (20.200.245.247)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes          // yes 만 로그인 없이 연결
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 208 bytes | 208.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:dx83/SSH.git
 * [new branch]      master -> master
```
