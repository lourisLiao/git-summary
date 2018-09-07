### 关于git syntax的一些总结
在工作中爬了好多坑，曾经因为使用了错误命令，清空了工作区内容，也就是一天甚至几天的写的代码没了，so...不妨
总结个人对git的用法

---

### 常用语法

#### 更新远程代码

* git fetch 
* git stash 
* git rebase
* git stash pop
* 解决冲突

以上是我早上回到公司常做的一个操作，git fetch更新远程代码，如果你本地工作区
有修改过，没有和远程仓库保持绝对的一致，则需要用git stash，这个命令会将你的本地修改暂时缓存起来，
并使你的本地代码指向最近一次的远程更新快照。其实这个命令就是保证git rebase能够顺利进行，在rebase
完成之后，再运行git stash pop将之前的本地修改过的代码检出，在这个时候如果你的本地代码修改比较大，
会出现冲突，需要手动合并冲突，因为git并不知道哪一些代码是你最终需要的。

***

#### 创建分支进行开发，完成后合并到主分支

* git stash (in 'master')
* git checkout -b 'dev' (create and switch to 'dev')
* git checkout master
* git merge dev

[update continue...]