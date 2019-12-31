---
date: 2017-12-08
title: GIT 问题记录--detached HEAD的解决方法
categories: 
- 技术
tags: 
- git
- 问题
---

今天使用git的时候莫名出现了一个问题
```bash
$ git push
fatal: You are not currently on a branch.
To push the history leading to the current (detached HEAD)
state now, use

    git push origin HEAD:<name-of-remote-branch>

```

这什么情况？

回想昨天做的git操作，好像强制更新了一次

```bash
git fetch --all
git reset --hard origin/master
```

使用了上面两条命令。但是是不是造成 `detached HEAD` 的原因就不知道了（git小白...）。

于是从网上查了一下 `detached HEAD`, 

> detached head是一种HEAD指针指向了某一个具体的 commit id，而不是分支的情况。在这个状态下进行的commit不会对你的远程分支产生影响。

解决办法也非常简单，把分支指向master就可以了：

```bash
$ git checkout master
Previous HEAD position was a3b5480... haha
Switched to branch 'master'
Your branch is behind 'origin/master' by 4 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

```

### 关于HEAD

什么是 `HEAD`,在网上找到了这样的答案：

> 转载 http://stackoverflow.com/questions/2304087/what-is-head-in-git 上的回答

> 你可以认为 HEAD(大写)是"current branch"(当下的分支)。当你用git checkout切换分支的时候，HEAD 修订版本重新指向新的分支。有的时候HEAD会指向一个没有分支名字的修订版本，这种情况叫”detached HEAD“

> head(小写)是commit对象的引用，每个head都有一个名字（分支名字或者标签名字等等），但是默认情况下，每个叫master的repository都会有一个head, 一个repository可以包含任意数量的head。在任何时候，只要这个head被选择成为”current head“，那么这个head就成了HEAD,总是大写

链接： [Git 中 HEAD 是什么东西，为什么会出现在分支里？](https://segmentfault.com/q/1010000000770497)
