## 合并冲突时出现问题处理


## 合并时发现处理有误，需要重新来过，而且没有commit
处理策略：终止合并操作

````
# abort the current in-progress merge 终止正在进行中的合并操作，回到合并之前
git merge --abort
````


## 合并之后已经commit过，但是commit之后没有新的commit
处理策略：返回到merge之前的点,重新merge


### 方法1

````
## 切到合并之前的节点
$ git checkout  [sha_of_before_merge]

## 重新合并
$ git merge xxxx

## 这个时候需要重新另存为一个分支，之前的分支不能用了。
$git checkout -b new_branch_name

````


### 方法2【推荐】
````
## 重新回退到合并之前的节点
$ git reset --hard [sha_of_before_merge]
## 重新合并
$ git merge xxxx
````


## 合并之后已经commit过了，同时又进行了新的commit，发现之前的合并有问题


### 方法1
先回退到合并之前的节点，创建临时分支，重新合并，再合并最新的修改

````
# 同上方法1，checkout到合并之前的节点，然后另存为另外一个分支；
$ git checkout -b branch-tmp [sha_of_before_merge]

# 重新进行合并操作
$ git merge master

# 切到branch，重新merge下branch-tmp
git checkout branch
git merge branch-tmp

````


### 方法2

revert合并操作，然后手动再合并一次【推荐】

````
# 把合并带来的变化撤销掉
$ git revert -m 1  [sha_of_wrong_merge]

# 手动重新merge并提交
$ git commit -m 'manual merge master fix merge error'

````