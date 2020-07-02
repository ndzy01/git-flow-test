# git-flow-test

# 创建 develop 分支

git branch develop
git push -u origin develop

# 创建功能分支 feature

## 通过 develop 新建 feaeure 分支

git checkout -b feature01 develop

## 或者, 推送至远程服务器:

git push -u origin feature

## 修改 md 文件

git status
git add .
git commit

# 完成功能分支 feature01

git pull origin develop
git checkout develop

#--no-ff：不使用 fast-forward 方式合并，保留分支的 commit 历史
#--squash：使用 squash 方式合并，把多次分支 commit 历史压缩为一次

git merge --no-ff feature01
git push origin develop

## 删除本地分支

git branch -d feature01

## 如果需要删除远程 feature 分支:

git push origin --delete feature01

# release

git checkout -b release-0.1.0 develop

git checkout master
git merge --no-ff release-0.1.0
git push

git checkout develop
git merge --no-ff release-0.1.0
git push

git branch -d release-0.1.0
git push origin --delete release-0.1.0

## 合并 master/devlop 分支之后，打上 tag

git tag -a v0.1.0 master
git push --tags
