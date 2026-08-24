PS C:\Users\user\Desktop\myProject> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.c
        hello.cpp
        hello.py

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\user\Desktop\myProject> git add hello.c
PS C:\Users\user\Desktop\myProject> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   hello.c

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.cpp
        hello.py

PS C:\Users\user\Desktop\myProject> git add hello.cpp hello.py
PS C:\Users\user\Desktop\myProject> git commit -m "建立還原點"
[master (root-commit) ec058c9] 建立還原點
 3 files changed, 10 insertions(+)
 create mode 100644 hello.c
 create mode 100644 hello.cpp
 create mode 100644 hello.py
PS C:\Users\user\Desktop\myProject> git add .
PS C:\Users\user\Desktop\myProject> git commit -m "hello world"
[master 1313929] hello world
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\user\Desktop\myProject> git log
commit 13139294d5b1f0034686d98f6eb79d6a28e3c8e7 (HEAD -> master)
Author: angus <ddarkimo7@gmail.com>
Date:   Mon Aug 24 21:12:56 2026 +0800

    hello world

commit ec058c90ce9aedf0d6fff0847323ba17c7fcd046
Author: angus <ddarkimo7@gmail.com>
Date:   Mon Aug 24 21:10:46 2026 +0800
PS C:\Users\user\Desktop\myProject> 
PS C:\Users\user\Desktop\myProject> git log --oneline
1313929 (HEAD -> master) hello world
ec058c9 建立還原點
PS C:\Users\user\Desktop\myProject> git diff
PS C:\Users\user\Desktop\myProject> git diff ec058c9 -- hello.c
diff --git a/hello.c b/hello.c
index 03b4b4f..3dea6d5 100644
--- a/hello.c
+++ b/hello.c
@@ -1,4 +1,4 @@
 #include <stdio.h>
 int main(){
-    printf("hello");
+    printf("hello world");
PS C:\Users\user\Desktop\myProject> git checkout ec058c9 -- hello.c
PS C:\Users\user\Desktop\myProject> git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   hello.c

PS C:\Users\user\Desktop\myProject> git commit -m "還原"
[master d911d14] 還原
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\user\Desktop\myProject> git log -- oneline
PS C:\Users\user\Desktop\myProject> git log --oneline
d911d14 (HEAD -> master) 還原
1313929 hello world
ec058c9 建立還原點
PS C:\Users\user\Desktop\myProject> git status
On branch master
nothing to commit, working tree clean
PS C:\Users\user\Desktop\myProject> git add .
PS C:\Users\user\Desktop\myProject> git commit -m "忽略"
[master 777aea7] 忽略
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
PS C:\Users\user\Desktop\myProject> git remote add origin https://github.com/ddarkimo7/angus.git
PS C:\Users\user\Desktop\myProject> git branch -M main
PS C:\Users\user\Desktop\myProject> git push -u origin main
info: please complete authentication in your browser...
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 12 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (12/12), 1.02 KiB | 52.00 KiB/s, done.
Total 12 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/ddarkimo7/angus.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
PS C:\Users\user\Desktop\myProject> git add .
PS C:\Users\user\Desktop\myProject> git commit -m "加入README"
[main afd6a59] 加入README
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
PS C:\Users\user\Desktop\myProject> git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 284 bytes | 284.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/ddarkimo7/angus.git
   777aea7..afd6a59  main -> main
PS C:\Users\user\Desktop\myProject> git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 951 bytes | 55.00 KiB/s, done.
From https://github.com/ddarkimo7/angus
   afd6a59..75f4077  main       -> origin/main
Updating afd6a59..75f4077
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\user\Desktop\myProject> 