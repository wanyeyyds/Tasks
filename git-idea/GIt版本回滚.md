# GIt版本回滚

### git回滚到指定版本并强制提交具体步骤

#####        第一步

- 执行 git log命令查看日志，获取需要回退的版本号

  ##### 第二步

  执行命令，如

  git reset  ---hard 4f5e9a90edeadcc45d85f43bd861a837fa7ce4c7 ，重置至指定版本的提交

  ##### 第三步

  执行 git push -f origin <branch_name> 强制提交当前版本号

## 一.reset、revert

在学习关于git版本回滚操作之前我们应该需熟练使用git log查看Git提交日志，同时也应学会使用git reflog查看Git提交日志。

PS D:\Work\git> git reflog
779743a (HEAD -> main) HEAD@{0}: reset: moving to 779743a502623109a1b8cd07ce168f1768bbe4b7
f2e6323 (origin/main) HEAD@{1}: reset: moving to f2e6323ffb48598cac55871208c99e95baf101de
f2e6323 (origin/main) HEAD@{2}: pull --tags origin main: Merge made by the 'ort' strategy.
ed685c6 HEAD@{3}: commit: 3
779743a (HEAD -> main) HEAD@{4}: reset: moving to HEAD~
0df18f6 HEAD@{5}: commit: 3
779743a (HEAD -> main) HEAD@{6}: commit: 2
5794575 HEAD@{7}: commit: 1111111
645dcaf HEAD@{8}: commit: 优化程序
上述提交日志由git reflog命令输出，可以明确了解到每一步进行了什么操作，以及对应的版本号，最核心的是保留了所有的操作记录。由于reset并没有产生新的提交记录因此git log并不能记录reset的操作。

### 1、使用git reset实现版本回滚

#### 3.1、工作区代码回滚

工作区代码回滚（丢弃修改的内容）：git checkout -- file丢弃某一个文件或者git checkout -- .丢弃全部修改内容。

注意：git checkout -- . 丢弃全部，也包括：新增的文件会被删除、删除的文件会恢复回来、修改的文件会回去。

#### 3.2、暂存区代码回滚

当我们修改完代码并执行了git add操作之后，已修改的内容会被存在暂存区。

此时回滚版本并还原内容：git reset --keep回滚暂存区全部文件。此操作相当于撤销git add操作。

此时回滚版本并还原内容：git reset HEAD file回滚单个文件或者git reset HEAD .回滚暂存区全部文件。此操作相当于撤销git add操作，并将工作区内容还原至上个版本内容。

回滚之后的代码会进入工作区，如需要丢弃修改的内容，可执行git checkout -- file

#### 3.3、本地仓库代码回滚

3.3.1、回滚到暂存区（相当于撤销git commit操作）：git reset --soft 779743a。

3.3.2、回滚到工作区（相当于撤销git commit及git add操作）：git reset --mixed 779743a。

3.3.3、回滚到工作区（相当于撤销git commit及git add操作）并且丢弃修改内容：git reset --hard 779743a。

3.3.4、撤销回滚步骤可先使用git reflog查看操作记录，并使用git reset --hard 0df18f6。

3.3.5、git reset --hard HEAD^回滚至上一次提交，工作区内容同步回滚。

3.3.6、git reset HEAD^回滚至上一次提交，工作区内容不会被修改。可使用git restore 文件还原到工作区。

#### 3.4、远程仓库代码回滚

第一步：首先需要进行本地代码的回滚，可参考前面内容。

第二步：强制推送到远程分支：git push -f origin dev。

需注意：

1、本地分支回滚后，版本将落后远程分支，必须使用强制推送覆盖远程分支，否则无法推送到远程分支。

2、gitLab所有分支默认是关闭强制推送功能的，如需进行强制推送，需开启对应功能。

#### 3.5.3个主要命令选项

--soft
  会将 HEAD 引用指向指定提交。索引和工作目录的内容保持不变。这个版本的命令有“最小”影响，只改变一个符号引用的状态使其指向一个新提交。

--mixed
  会将 HEAD 指向指定提交。索引内容也跟着改变以符合指定提交的树结构，但是工作目录中的内容保持不变。这个版本的命令将索引变成你刚刚暂存该提交全部变化时的状态，它会显示工作目录中还有什么修改。–mixed 是 git reset 的默认模式。

--hard
  这条命令将 HEAD 引用指向给定提交。索引的内容也跟着改变以符合给定提交的树结构。此外，工作目录的内容也随之改变以反映给定提交表示的树的状态。当改变工作目录的时候，整个目录结构都改成给定提交对应的样子。做的修改都将丢失，新文件将被删除。在给定提交中但不在工作目录中的文件将恢复回来。

### 2、使用git revert实现版本回滚

PS D:\Work\git> git reflog
5530e50 (HEAD -> main, origin/main) HEAD@{0}: commit: Revert "2"
f2e6323 HEAD@{1}: pull --tags origin main: Fast-forward
779743a HEAD@{2}: reset: moving to 779743a
0df18f6 HEAD@{3}: reset: moving to 0df18f6
779743a HEAD@{4}: reset: moving to 779743a
0df18f6 HEAD@{5}: reset: moving to 0df18f6
0df18f6 HEAD@{6}: reset: moving to 0df18f6
779743a HEAD@{7}: reset: moving to 779743a502623109a1b8cd07ce168f1768bbe4b7
f2e6323 HEAD@{8}: reset: moving to f2e6323ffb48598cac55871208c99e95baf101de
f2e6323 HEAD@{9}: pull --tags origin main: Merge made by the 'ort' strategy.
ed685c6 HEAD@{10}: commit: 3
通过上述信息可以看出，git revert会以回滚内容创建新的版本，很大程度上在进行代码提交时会产生冲突。

git reset 和 git checkout 命令同样可以接受一个可选的文件路径作为参数,这样可以将操作限制在一个单独的文件中，但是git revert并不能将惭怍限制在指定文件中。

### 三、git log命令的使用

git log输出的内容比较全，可以看到操作者，操作时间，提交备注，版本号等信息。很多情况下我们并不需要这么多的信息，则可使用git log --pretty对操作日志进行格式化。

使用git log --pretty=oneline简化日志信息。

PS D:\Work\git> git log --pretty=oneline
f2e6323ffb48598cac55871208c99e95baf101de (HEAD -> main, origin/main) Merge branch 'main' of http://10.188.186.140/test/git-test
ed685c6dfeace65b7ae5343170230a45def1c327 3
0df18f689bc98f08765ff9ba3e9604b9acb0f3b6 3
779743a502623109a1b8cd07ce168f1768bbe4b7 2
579457591bf607010932c3fde6bfd5558765ffd0 1111111
645dcaf10cf244505ebd5c1a8407e5dfd4aae50e 优化程序
简化之后的日志信息中我们可以快速找到某一次提交记录的版本号。

使用定制化输出提交日志

git log --pretty=format:"%h - %an, %ar : %s")

[李](https://blog.csdn.net/qq_16221009/article/details/12549063)