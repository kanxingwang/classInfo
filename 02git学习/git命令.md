# git 命令 #

git 学习参照廖雪峰个人网站。[廖雪峰git](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

- **任务1**:在learnGit 项目上develop分支上提交自己的helloWorld 程序。
- **任务2**:新建一个分支，并且在新分支上新建一个项目。

## git 操作 ##
1.首先先同步主分支master代码

先切换到主分支master

git fetch

git rebase origin/master

2.新建分支

git checkout(或者别名co) -br 新分支名

3.修改代码

4.提交新分支代码修改

git add 修改的文件

git commit -m '修改注释'
git push origin 新分支名:新分支名(一般本地和远程用的分支名一致)，注意冒号

5.合并新分支修改到主分支master

git checkout master

git fetch

git rebase origin/master

git merge origin/新分支名

有冲突解决冲突

git add 冲突文件

git commit -m '冲突文件注释'

git push origin master

6.如果需要发版就打本地tag和推送远程tag

git tag （查看当前tag情况）

git tag 新tag名(一般在之前最后一个tag基础上加1)

git push origin 新tag名

7.检查

gitk (可以查看历次提交和修改情况)

8.放弃本地commit

git log找到还原到的版本号

git reset --soft  版本号                     可以还原到该版本，本地源码不会丢失

git reset .                                            可以放弃本地add(注意有个点)

git reset --hard 版本号                    可以还原到该版本，本地源码也会丢失

9.放弃本地修改，还没add和提交

git co 文件

git  co .    标示放弃本地全部修改（注意有个点）


st = status

ci = commit

br = branch

co = checkout


删除本地和远程分支：

git branch -D xxx

git push origin :xxx

删除本地和远程tag:

git tag -d xxx

git push origin :refs/tags/xxx

 

暂存分支未提交本地代码库代码

git stash

打开暂存代码

git stash pop

本地创建分支并且推送到远程
git co -b saoma_bug 

git push origin local_branch:remote_branch 

合并多次提交

git rebase -i HEAD~3
