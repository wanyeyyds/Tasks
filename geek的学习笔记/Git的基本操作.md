# Git的基本操作

## --[来自廖雪峰](https://www.liaoxuefeng.com/wiki/896043488029600)

Git是目前世界上最先进的分布式版本控制系统（没有之一）。

### 那什么是版本控制系统？

不但能自动帮我记录每次文件的改动，还可以让同事协作编辑，这样就不用自己管理一堆类似的文件了，也不需要把文件传来传去。如果想查看某次改动，只需要在软件里瞄一眼就可以.

这个软件能记录每次文件的改动：

版本 文件名    用户         说明                                     日期
1 service.doc 张三 删除了软件服务条款5        7/12 10:38
2 service.doc 张三 增加了License人数限制     7/12 18:09
3 service.doc 李四 财务部门调整了合同金额   7/13 9:51
4 service.doc 张三 延长了免费升级周期          7/14 15:17
Linus一直痛恨的CVS及SVN都是集中式的版本控制系统，而Git是分布式版本控制系统

# 操作来了

什么是版本库呢？版本库又名仓库，英文名repository，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

所以，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录：

$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
pwd命令用于显示当前目录。在我的Mac上，这个仓库位于/Users/michael/learngit。

 如果你使用Windows系统，为了避免遇到各种莫名其妙的问题，请确保目录名（包括父目录）不包含中文。
第二步，通过git init命令把这个目录变成Git可以管理的仓库：

$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），细心的读者可以发现当前目录下多了一个.git的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。

如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见。

也不一定必须在空目录下创建Git仓库，选择一个已经有东西的目录也是可以的。不过，不建议你使用自己正在开发的公司项目来学习Git，否则造成的一切后果概不负责。

把文件添加到版本库

首先这里再明确一下，所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外。版本控制系统可以告诉你每次的改动，比如在第5行加了一个单词“Linux”，在第8行删了一个单词“Windows”。而图片、视频这些二进制文件，虽然也能由版本控制系统管理，但没法跟踪文件的变化，只能把二进制文件每次改动串起来，也就是只知道图片从100KB改成了120KB，但到底改了啥，版本控制系统不知道，也没法知道。

不幸的是，Microsoft的Word格式是二进制格式，因此，版本控制系统是没法跟踪Word文件的改动的，前面我们举的例子只是为了演示，如果要真正使用版本控制系统，就要以纯文本方式编写文件。

因为文本是有编码的，比如中文有常用的GBK编码，日文有Shift_JIS编码，如果没有历史遗留问题，强烈建议使用标准的UTF-8编码，所有语言使用同一种编码，既没有冲突，又被所有平台所支持。

使用Windows的童鞋要特别注意：

千万不要使用Windows自带的记事本编辑任何文本文件。原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，你会遇到很多不可思议的问题，比如，网页第一行可能会显示一个“?”，明明正确的程序一编译就报语法错误，等等，都是由记事本的弱智行为带来的。建议你下载Visual Studio Code代替记事本，不但功能强大，而且免费！

言归正传，现在我们编写一个readme.txt文件，内容如下：

Git is a version control system.
Git is free software.
一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。[图片]([![xbSY7V.jpg](https://s1.ax1x.com/2022/11/02/xbSY7V.jpg)](https://imgse.com/i/xbSY7V))

![微信图片_20221102203836](C:\Users\86191\Videos\bilibili\微信图片_20221102203836.jpg)![微信图片_20221102203841](C:\Users\86191\Videos\bilibili\微信图片_20221102203841.jpg)

![微信图片_20221102203846](C:\Users\86191\Videos\bilibili\微信图片_20221102203846.jpg)

![微信图片_20221102203853](C:\Users\86191\Videos\bilibili\微信图片_20221102203853.jpg)

和把大象放到冰箱需要3步相比，把一个文件放到Git仓库只需要两步。

第一步，用命令git add告诉Git，把文件添加到仓库：

$ git add readme.txt
执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令git commit告诉Git，把文件提交到仓库：

$ git commit -m "wrote a readme file"
[master (root-commit) eaadf4e] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
简单解释一下git commit命令，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

嫌麻烦不想输入-m "xxx"行不行？确实有办法可以这么干，但是强烈不建议你这么干，因为输入说明对自己对别人阅读都很重要。实在不想输入说明的童鞋请自行Google，我不告诉你这个参数。

git commit命令执行成功后会告诉你，1 file changed：1个文件被改动（我们新添加的readme.txt文件）；2 insertions：插入了两行内容（readme.txt有两行内容）。

为什么Git添加文件需要add，commit一共两步呢？因为commit可以一次提交很多文件，所以你可以多次add不同的文件，比如：

$ git add file1.txt
$ git add file2.txt file3.txt
$ git commit -m "add 3 files."
疑难解答

Q：输入git add readme.txt，得到错误：fatal: not a git repository (or any of the parent directories)。

A：Git命令必须在Git仓库目录内执行（git init除外），在仓库目录外执行是没有意义的。

Q：输入git add readme.txt，得到错误fatal: pathspec 'readme.txt' did not match any files。

A：添加某个文件时，该文件必须在当前目录下存在，用ls或者dir命令查看当前目录的文件，看看文件是否存在，或者是否写错了文件名。

小结

现在总结一下今天学的两点内容：

初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

使用命令git add <file>，注意，可反复多次使用，添加多个文件；
使用命令git commit -m <message>，完成。

![微信图片_20221102203814](C:\Users\86191\Videos\bilibili\微信图片_20221102203814.jpg)

![微信图片_20221102203822](C:\Users\86191\Videos\bilibili\微信图片_20221102203822.jpg)

![微信图片_20221102203829](C:\Users\86191\Videos\bilibili\微信图片_20221102203829.jpg)

#### 关于vim

github上也有关于vim的介绍：https://github.com/vim/vim 
简书上关于vim的学习： Vim 从入门到精通
解决git bash中出现vim的情况
emmmmm……到目前为止还没细看以上vim的内容，现在记录这篇博客的重点还是在使用Git中，解决vim这个问题。
看到很多的解决方法一上来就是按Esc键退出插入模式。但是进入vim编辑器的时候，并不是插入模式的。 
所以第一步就是要输入命令进入插入模式。
命令说明
i 实现的是在光标之前的插入 
I 大写的i实现在光标所在行的最前面插入 
a 实现在光标后插入 
A 实现在光标所在行的行尾插入 
o 实现在光标所在行的上方插入新行 
O 是现在光标坐在行的下方插入新行 
进入插入模式之后就可以进行编辑了。 
编辑完了就可以按Esc键退出插入模式，然后输出:wq或者ZZ即可退出vim编辑器，回到git bash界面。
方法步骤是挺简单的。但是还是得了解一下git中vim的命令是啥意思。
git中vim的命令
命令说明
:w 保存编辑后的文件内容，但不退出vim编辑器。这个命令的作用是把内存缓冲区中的数据写到启动vim时指定的文件中。 
:w! 强制写文件，即强制覆盖原有文件。如果原有文件的访问权限不允许写入文件，例如，原有的文件为只读文件，则可使用这个命令强制写入。但是，这种命令用法仅当用户是文件的属主时才适用，而超级用户则不受此限制。 
:wq 保存文件内容后退出vim编辑器。这个命令的作用是把内存缓冲区中的数据写到启动vim时指定的文件中，然后退出vim编辑器。另外一种替代的方法是用ZZ命令。 
:wq! 强制保存文件内容后退出vim编辑器。这个命令的作用是把内存缓冲区中的数据强制写到启动vim时指定的文件中，然后退出vim编辑器。 
ZZ 使用ZZ命令时，如果文件已经做过编辑处理，则把内存缓冲区中的数据写到启动vim时指定的文件中，然后退出vim编辑器。否则只是退出vim而已。注意，ZZ命令前面无需加冒号“：”，也无需按Enter键。 
:q 在未做任何编辑处理而准备退出vim时，可以使用此命令。如果已做过编辑处理，则vim不允许用户使用“:q”命令退出，同时还会输出下列警告信息：No write since last change (:quit! overrides) 
:q! 强制退出vim编辑器，放弃编辑处理的结果。如果确实不需要保存修改后的文件内容，可输入“:q!”命令，强行退出vim编辑器。 
:w filename 把编辑处理后的结果写到指定的文件中保存 
:w! filename 把编辑处理后的结果强制保存到指定的文件中，如果文件已经存 在，则覆盖现有的文件。 
:wq! filename 把编辑处理后的结果强制保存到指定的文件中，如果文件已经存在，则覆盖现有文件，并退出vim编辑器。 
备注：以上表格内容参考自简书中的一篇文章：git中的vim命令，侵删！

[转载](https://blog.csdn.net/sinat_39571186/article/details/78911814?utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-2.no_search_link&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-2.no_search_link)

```

```

