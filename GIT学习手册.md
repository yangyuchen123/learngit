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
+ git diff告诉文件的改动
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

+ 现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit -m"massage"
## 远程仓库
### 添加远程仓库
+ ssH KEY在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件
+ 第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
+ $ git remote add origin git@github.com:yangyuchen123/learngit.git关联githud
+ $ git push -u origin master(推送给github)
+ 把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

+ 从现在起，只要本地作了提交，就可以通过命令：

$ git push origin master
+ 如果添加的时候地址写错了，或者就是想删除远程库，可以用git remote rm <name>（一般是origin）命令。使用前，建议先用git remote -v查看远程库信息：
+ 此处的“删除”其实是解除了本地和远程的绑定关系，并不是物理上删除了远程库。远程库本身并没有任何改动。要真正删除远程库，需要登录到GitHub，在后台页面找到删除按钮再删除。

### 从远程库克隆
+ 首先，登陆GitHub，创建一个新的仓库，名字叫gitskills：
+ $ git clone git@github.com:yangyuchen123/gitskills.git（克隆本地库）
+ 你也许还注意到，GitHub给出的地址不止一个，还可以用https://github.com/michaelliao/gitskills.git这样的地址。实际上，Git支持多种协议，默认的git://使用ssh，但也可以使用https等其他协议。
使用https除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。

