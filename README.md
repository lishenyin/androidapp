# androidapp
touch readme
git add readme.txt
git add .
git commit -m "comments"
git checkout -- README //只适用没有添加的动作文件
git status
git diff
git log
git checkout -file
git reset HEAD -file //已经添加了，需要撤销添加，才能适用checkout 还原


版本回退

git reset --hard HEAD^ //直接回退已经提交的上一个版本

后悔回退
git reflog //查看操作日志，每个日志回显版本号

git reset --hard ad2080c
