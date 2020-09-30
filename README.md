### Git Homework - navjot bansal

## Git Blame

#### From first user (shadow) made a file touch.cpp
```console
[shadow@master oracle_training]$ vi touch.cpp
[shadow@master oracle_training]$ git add touch.cpp 
[shadow@master oracle_training]$ git config --global user.email "shadow@gmail.com"
[shadow@master oracle_training]$ git config --global user.name "shadow"
[shadow@master oracle_training]$ git commit -m "base c++"
[master 64365c0] base c++
 1 file changed, 6 insertions(+)
 create mode 100644 touch.cpp
[shadow@master oracle_training]$ git push origin master
Username for 'https://github.com': navjotbansal
Password for 'https://navjotbansal@github.com': 
Counting objects: 4, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 367 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/NavjotBansal/oracle_training
   a43f4c3..64365c0  master -> master
[shadow@master oracle_training]$ ls
story2.txt  story.txt  touch.cpp
[shadow@master oracle_training]$ cat touch.cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
  return 0;  
}
```
#### From first user (navjotbansal) made a file touch.cpp
```console
[root@master test]# git pull origin master
From https://github.com/NavjotBansal/oracle_training
 * branch            master     -> FETCH_HEAD
Merge made by the 'recursive' strategy.
 touch.cpp | 6 ++++++
 1 file changed, 6 insertions(+)
 create mode 100644 touch.cpp
[root@master test]# ls
dev.txt  story.txt  story2.txt  touch.cpp
[root@master test]# vi touch.txt
[root@master test]# rm touch.txt 
rm: remove regular empty file 'touch.txt'? 
[root@master test]# vi touch.cpp
[root@master test]# git add touch.cpp 
[root@master test]# git commit -m "added headers and IO file"
[master caaab03] added headers and IO file
 1 file changed, 3 insertions(+)
[root@master test]# git push origin master
Username for 'https://github.com': navjotbansal	
Password for 'https://navjotbansal@github.com': 
Counting objects: 11, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (7/7), done.
Writing objects: 100% (8/8), 921 bytes | 0 bytes/s, done.
Total 8 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/NavjotBansal/oracle_training.git
   64365c0..caaab03  master -> master
[root@master test]# git blame touch.cpp 
64365c09 (shadow       2020-09-29 04:05:09 +0530 1) #include<bits/stdc++.h>
64365c09 (shadow       2020-09-29 04:05:09 +0530 2) using namespace std;
caaab03c (navjotbansal 2020-09-29 04:10:10 +0530 3) #define vi vector<int>
64365c09 (shadow       2020-09-29 04:05:09 +0530 4) int main()
64365c09 (shadow       2020-09-29 04:05:09 +0530 5) {
caaab03c (navjotbansal 2020-09-29 04:10:10 +0530 6)   ios_base::sync_with_stdio(
caaab03c (navjotbansal 2020-09-29 04:10:10 +0530 7)   cin.tie(false);cout.tie(fa
64365c09 (shadow       2020-09-29 04:05:09 +0530 8)   return 0;  
64365c09 (shadow       2020-09-29 04:05:09 +0530 9) }
```
## Git grep 
```console
[root@master test]# git grep "it"
story.txt:right commit
story2.txt:wrong commit
touch.cpp: #include<bits/stdc++.h>
touch.cpp:  ios_base::sync_with_stdio(false);
[root@master test]# 
```
## Git describe

```console
[root@master test]# git tag -a v1.0 -m "version1.0"
[root@master test]# git push origin --tags
Username for 'https://github.com': navjotbansal
Password for 'https://navjotbansal@github.com': 
Counting objects: 1, done.
Writing objects: 100% (1/1), 154 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/NavjotBansal/oracle_training.git
 * [new tag]         v1.0 -> v1.0
[root@master test]# touch second_version.py
[root@master test]# vi second_version.py
[root@master test]# git add second_version.py 
[root@master test]# git commit -m "uuid"
[master c32d9a9] uuid
 1 file changed, 4 insertions(+)
 create mode 100644 second_version.py
[root@master test]# git push origin master
Username for 'https://github.com': navjotbansal
Password for 'https://navjotbansal@github.com': 
Counting objects: 4, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 312 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/NavjotBansal/oracle_training.git
   caaab03..c32d9a9  master -> master
[root@master test]# git tag -a v1.1 -m "version1.1"
[root@master test]# git show-ref
11a2ed6a7c0cec8bb63dfec211ec56bad179ae14 refs/heads/dev
c32d9a9b57610c7268b079d1c0dbec17ef7346c4 refs/heads/master
c32d9a9b57610c7268b079d1c0dbec17ef7346c4 refs/remotes/origin/master
d9e183ce8ea7134f1a46c14104c00cfa98de6db9 refs/tags/v1.0
e21744c39d9617ea7c9ee2ac89c92cf1d8c86bf0 refs/tags/v1.1
[root@master test]# git push origin --tags
Username for 'https://github.com': navjotbansal
Password for 'https://navjotbansal@github.com': 
Counting objects: 1, done.
Writing objects: 100% (1/1), 155 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/NavjotBansal/oracle_training.git
 * [new tag]         v1.1 -> v1.1
[root@master test]# git ls-files
dev.txt
second_version.py
story.txt
story2.txt
touch.cpp
[root@master test]# git tag -l
v1.0
v1.1
[root@master test]# git describe
v1.1
```
## Git Bisect
#### ( after the version 1.0 tag uuid.py file was added and pushed to v1.1 ) 
#### as version 1.0 was good 
#### so git showed uuid file to the bug ridden code of version post 1.0

```console
[root@master test]# git bisect start 
[root@master test]# git bisect bad
[root@master test]# git bisect good v1.0
c32d9a9b57610c7268b079d1c0dbec17ef7346c4 is the first bad commit
commit c32d9a9b57610c7268b079d1c0dbec17ef7346c4
Author: navjotbansal <nav@bansal.com>
Date:   Tue Sep 29 04:34:17 2020 +0530

    uuid

:000000 100644 0000000000000000000000000000000000000000 82994204e210f219a4efdb7664f18435fa0f4733 A	second_version.py
```

