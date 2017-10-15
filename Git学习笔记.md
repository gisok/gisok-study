# Git 学习笔记

[TOC]

## 创建文件夹
## status:查看状态

```
git status
```

## init:初始化该文件夹为GIT仓库
```
    git init
```

所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外.

Microsoft的Word格式是二进制格式，因此，版本控制系统是没法跟踪Word文件的改动的.

强烈建议使用标准的UTF-8编码，所有语言使用同一种编码，既没有冲突，又被所有平台所支持
千万不要使用Windows自带的记事本编辑任何文本文件。原因是保存UTF-8编码文件时在每个文件开头添加了0xefbbbf（十六进制）字符。

## add:把文件添加到仓库
建立或拷贝文件到文件夹
执行 GIT add
```
git add readme.txt
```

？提交多个文件？

## commit:把文件提交到仓库
建立或拷贝文件到文件夹
执行 GIT add
```
git commit -m "提交第一个文件 readme.txt"
```

commit可以一次提交很多文件


## diff:查看文件有什么改动

```
git diff readme.txt
```

## log：查看版本记录

```
git log
```


## reset:设置当前版本

* 当前版本标记为 HEAD,上一个版本为 HEAD^,上上一个为 HEAD^^, 上上上一个为 HEAD~3

```
git reset --hard HEAD^
```

* 根据版本号设定回到哪个版本

```
git reset --hard bcc91a
```


## reflog：查看版本设定记录

```
git reflog
```

## checkout -- ：单个文件撤销修改
* 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

* 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

* 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。


## rm：删除版本库中的文件

```
git rm readme.txt
```

## remote add : 关联远程库

```
$ git remote add origin git@github.com:michaelliao/learngit.git
```

## push : 推送本地库到远程库

```
git push -u origin master
```

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

从现在起，只要本地作了提交，就可以通过命令：

```
$ git push origin master
```

把本地master分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！

## branch: 查看分支

```
$ git branch
```


## branch 分支名: 创建分支

```
$ git branch dev
```


## checkout -b : 创建并切换分支

```
$ git checkout -b dev
```



## ?怎么使用汉字文件名?

通过将Git配置变量 core.quotepath 设置为false，就可以解决中文文件名称在这些Git命令输出中的显示问题，

```        
$ git config --global core.quotepath false
$ git status -s
?? 说明.txt
```


## 注意

### 文件名大小写敏感

### 概念

* 工作区
    电脑里能看到的目录，比如我的learngit文件夹就是一个工作区
* 版本库
    隐藏目录.git，是Git的版本库。
    Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD
* add 工作区 -> 暂存区
* commit 暂存区 -> 当前分支
* Git跟踪并管理的是修改，而非文件
* 最早，肯定只有一台机器有一个原始版本库，此后，别的机器可以“克隆”这个原始版本库，而且每台机器的版本库其实都是一样的，并没有主次之分
* 实际情况往往是这样，找一台电脑充当服务器的角色，每天24小时开机，其他每个人都从这个“服务器”仓库克隆一份到自己的电脑上，并且各自把各自的提交推送到服务器仓库里，也从服务器仓库中拉取别人的提交。这个服务器可以是GITHub.
* GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库
* HEAD指向当前分支,当前分支为master
![pic1](https://www.liaoxuefeng.com/files/attachments/0013849087937492135fbf4bbd24dfcbc18349a8a59d36d000/0)
    

