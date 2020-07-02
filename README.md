# git-flow-test

#--no-ff：不使用 fast-forward 方式合并，保留分支的 commit 历史

#--squash：使用 squash 方式合并，把多次分支 commit 历史压缩为一次

# 创建 develop 分支

1. 创建 develop 分支并推送到远端

   git branch develop

   git push -u origin develop

# 功能分支 feature

1. 通过 develop 新建 feaeure 分支

   git checkout -b feature01 develop

   或者,直接推送至远端服务

   git push -u origin feature01

2. feature01 分支功能完成

   git pull origin develop

   git checkout develop

   git merge --no-ff feature01

   git push origin develop

3. 删除本地和远程分支(可删可不删)

   git branch -d feature01

   删除远程 feature 分支:

   git push origin --delete feature01

# release

1. 通过 develop 新建 release 分支

   git checkout -b release-0.1.0 develop

2. 合并 release 到 master 和 develop

   git pull origin master

   git checkout master

   git merge --no-ff release-0.1.0

   git push

   git pull origin develop

   git checkout develop

   git merge --no-ff release-0.1.0

   git push

3. 删除本地和远程分支

   git branch -d release-0.1.0

   git push origin --delete release-0.1.0

## 合并 master/devlop 分支之后，打上 tag

1. git tag -a v0.1.0 master -m "v0.1.0"

2. git push --tags

# hotfix

1. git checkout -b hotfix-0.1.1 master

2. 合并

   git pull origin master

   git checkout master

   git merge --no-ff hotfix-0.1.1

   git push

   git pull origin develop

   git checkout develop

   git merge --no-ff hotfix-0.1.1

   git push

3. 删除分支

   git branch -d hotfix-0.1.1
   
   git push origin --delete hotfix-0.1.1

4. 打上补丁

   git tag -a v0.1.1 master -m "v0.1.1"

   git push --tags
