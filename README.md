# androidapp
touch readme
git add readme.txt
git add .
git commit -m "comments"
git checkout -- README //只适用没有添加的动作文件
git status
git diff
git log
git log --pretty=oneline
git checkout -file
git reset HEAD -file //已经添加了，需要撤销添加，才能适用checkout 还原


版本回退

git reset --hard HEAD^ //



后悔回退
git reflog //查看操作日志，每个日志回显版本号

git reset --hard ad2080c


操作远程仓库

创建分支(后者创建同时会切换分支):
git branch v1.0.3 或 git checkout -b v1.0.4

查看版本库中所有分支：
git branch -a

切换到某一分支：
git checkout v1.0.3

删除某一分支：
git branch -D v1.0.4

合并分支
 git merge v1.0.3
 
 ---------------------------------------------------
 本地仓库与远程仓库同步问题
 我们先对我们的本地仓库做一点点修改，接着git add和git commit本地准备后，然后：
 
 git push origin master 或者直接 git push
 
 
有同步到服务器，肯定有服务器同步到本地是吧，很简单，就一个
git pull


git checkout -- readme.txt //总之，就是让这个文件回到最近一次git commit或git add时的状态。 丢弃工作区的修改


git reset HEAD file //可以把暂存区的修改撤销掉（unstage），重新放回工作区, git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本。


git rm file // 删除文件，同样使用git checkout -- file 还原


 git remote add origin git@github.com:lishenyin/androidapp.git//将本地仓库与远程库关联
 
 git push -u origin master//将本地库，推送到远程库
 
 
 
 git 协议切换

git remote rm origin 
git remote add origin 协议地址
如 git remote add origin git@github.com:lishenyin/androidapp.git

分支---------------------------
查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>


冲突解决----------------------------
查看分支冲突解决的情况：

git log --graph --pretty=oneline --abbrev-commit


合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。


BUG--------------------
修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；

当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。

feature---------------

开发一个新feature，最好新建一个分支；

如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。


多人协作---------------
git push origin master//推送到远程仓库
git push origin dev //开发分支，需要远程同步

master分支是主分支，因此要时刻与远程同步；

dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；

bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；

feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。


抓取--------------
$ git checkout -b dev origin/dev

git branch --set-upstream dev origin/dev//原因是没有指定本地dev分支与远程origin/dev分支的链接

查看远程库信息，使用git remote -v；

本地新建的分支如果不推送到远程，对其他人就是不可见的；

从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；

在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；

从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。

TAG-----------------

命令git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id；

git tag -a <tagname> -m "blablabla..."可以指定标签信息；

git tag -s <tagname> -m "blablabla..."可以用PGP签名标签；

命令git tag可以查看所有标签。

tag 操作---------------------

命令git push origin <tagname>可以推送一个本地标签；

命令git push origin --tags可以推送全部未推送过的本地标签；

命令git tag -d <tagname>可以删除一个本地标签；

命令git push origin :refs/tags/<tagname>可以删除一个远程标签。
