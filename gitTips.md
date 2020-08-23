# 常用Git命令

## 本地命令

```shell
# 初始化一个 git
git init
## 初始化之后有有 .git 文件
## VS Code中新建文件之后，会有一个"U"，表示untracked

# 查看git文件的状态
git status
# 简便查询信息
git status -s
## "A"表示当前文件是暂存状态，但是没有提交

# 有三个用处：
# 1、将一个未跟踪的文件加入git跟踪；
# 2、将一个修改状态的文件加入暂存区；
# 3、将有冲突的文件标记为冲突已解决。
git add
git add filename.format
## VS Code中用小加号(stage changes)
## 这个命令也可以将发生冲突的文件标记为冲突已解决

# 将暂存区的做一次提交
git commit
git commit -m 'commitMessage'
# 分两步提交
git add filename.format && git commit -m 'commitMessage'
# 快速提交
git commit -am 'commitMessage'

# 取消对文件的修改
git restore
git restore filename.format

# 切换其他分支
git checkout
# 创建并切换分支
git checkout -b branchName

# 新建其他的分支
git branch
# 查看所有分支和当前分支
git branch -l
# 创建并切换分支
git branch branchName && git chechout branchName
# 简便写法
git checkout -b branchName

# 合并其他分支（经常需要解决冲突）
git merge
## 处于现在的分支，合并另一个
git merge branchName
# VS Code中使用command palate，搜索merge；有冲突的话直接点修改
## "C"表示conflict，表示文件有冲突

# 临时保存当前工作的分支，切换到其他分支
# 直接git stash
git stash
## 不能带着脏的状态到别的分支
# 恢复之前工作的内容
git stash pop
# VS Code中点"..."，点stash；之后再pop stash

# 查看哪些地方对文件做了修改
git diff
git diff filename.format
```

## 远程命令

```shell
# 用于clone一个远程仓库代码
git clone SSH链接
## commit之后直接git push

# 将本地分支的commit提交到远程分支
git push
## VS Code中的操作到commit及之前都是一样的，之后点上方的" … "，进行提交

# 相当于git stash + git merge，用于拉取远程项目的更新，以及将更新合并到本地分支
git pull
git pull && git push
## 一般在做项目提交的时候要先pull再push
## VS Code中选择 "Sync" 选项
```
