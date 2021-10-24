# GIT学习手册
+ 转换文件夹 cd learngit
+ git status
  git status命令可以让我们时刻掌握仓库当前的状态
+ 版本控制系统肯定有某个命令可以告诉我们历史记录，在Git中，我们用git log命令查看：
## 创建库
+ $ mkdir learngit(创建库)
  $ cd learngit
  $ pwd(显示当前目录)
  $ git init
_ git diff告诉文件的改动
## 文件添加到库(更新库)
+ 一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。
+ $ git add readme.txt
+ $ git commit -m "wrote a readme file"(注释)
+ git status
  git status命令可以让我们时刻掌握仓库当前的状态
## 时光穿梭
+ 版本控制系统肯定有某个命令可以告诉我们历史记录，在Git中，我们用git log命令查看
+ $ git reset --hard HEAD^(一个^回一级)
+ $ git reset --hard 1094a(通过版本号回到未来)
+ Git提供了一个命令git reflog用来记录你的每一次命令：
+ 