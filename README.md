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
git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：


git branch命令查看当前分支：