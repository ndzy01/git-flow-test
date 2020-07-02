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

git branch -d some-feature

## 如果需要删除远程 feature 分支:

git push origin --delete feature
