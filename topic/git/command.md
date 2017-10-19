## 常用命令


## 初始化
````
# 初始化git
$ git init
# 添加readme和.gitignore配置

# 本地git跟远程git关联
$ git remote add origin git_url

# 加上-u参数,Git就会把本地的master分支和远程的master分支进行关联起来,
# 我们以后的push操作就不再需要加上-u参数了
$ git push -u origin master

# 克隆git代码到本地
git clone git_url 本地文件夹名（可省略）

# 推荐clone时采用ssh格式的url，经过配置之后，不用每次输入密码
````


## 提交
````
# 查看状态
$ git status

# 提交
$ git commit -am '本次提交的修改描述'

# 查看日志
$ git log --pretty=oneline

# 与某个提交点对比
$ git diff [sha_commit]

````


## 查看分支，创建分支

````
# git branch命令的-r选项，可以用来查看远程分支，-a选项查看所有分支
$ git branch # 列出所有本地分支
$ git branch -r # 列出所有远程分支
$ git branch -a # 列出所有分支

# 查看本地分支与远程分子的关联关系
$ git branch -vv

# 拉取远程分支并创建本地分支,同时把新分支与远程分支建立追踪关系
$ git checkout -b br1 origin/br1

# 基于当前状态创建一个分支
$ git checkout -b branch_name

# 手动建立本地分支与远程分支的追踪关系
$ git checkout br1
$ git branch -u origin/br1 或 git branch --set-upstream  origin/br1

````


## 推送和拉取远程分支

````
# pull/fetch 拉取远程分支或更新远程分支到本地分支
$ git fetch origin # 将本地的远端和远端进行同步
$ git merge origin/master # 将本地的远端合并到本地分支

$git pull origin # 这相当于上面两条命令

# 如果当前分支与远程分支存在追踪关系，git pull/push 就可以省略远程分支
$ git push origin

# 如果当前分支与远程分支不建立追踪关系，git push
$ git push origin br3:br3
# 或
$ git push -u origin br3 或 git push --set-upstream origin br3
````


## 分支的删除

````
$ git branch -a # 查看本地和远程所有分支，确定需要删除的分支名称
$ git branch -D branchName  # 在本地删除此分支
$ git push origin --delete branchName  # 在远程删除此分支。
$ git branch -a  # 查看是否删除干净，一般会发现还存在该分支名称。

# 删除本地看到的远程已经删除的分支
$ git remote prune origin

````