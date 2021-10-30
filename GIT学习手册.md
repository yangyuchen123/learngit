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

## 撤销修改
- 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file（文件名加格式）。

- 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
$ git reset HEAD readme.txt

+ 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

## 删除文件
- 一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用rm命令删了：

$ rm test.txt