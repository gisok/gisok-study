##一、课题组织架构
###1. 管理模式
大数据课题组采用矩阵式管理，通过横向和纵向的管理模式，提升课题组的工作效率，打破部门壁垒，达到人员的充分调配。
###2. 团队设置
大数据课题组，下设设置13个小组，分别为：

产品组、JAVA一组（平台方向）、JAVA二组（业务方向）、前端一组（平台方向）、前端二组（业务方向）、大数据组、可视化组、UI组、数据处理组、运维组、测试组、技术支持组和管理后勤组。

###3. 协作模式
大数据课题组以产品为主线，协调各组人力资源，在开发完成后，人力资源回归本小组进行下一次的分配。
###4. 课题组织结构图
>表格中颜色不同代表不同类别员工，<font color=#1E90FF>专业技术人员</font>、<font color=#EEAD0E>技术管理人员</font>、<font color =#008B45>管理后勤人员</font>。

![](/Users/shou/Desktop/1.jpg)

<br>
##二、课题组产品任务运作流程
###5. 立项
由课题负责人牵头协调产品组对产品进行论证（即可行性分析）后，产品组指派一名产品经理负责该产品协调编写可行性分析报告、项目申报书、需求调研计划、需求确认表、用户需求说明、需求规格说明书、竞品分析等相关文件，评审通过后交至QA。
###6. 设计
立项完成后，由架构师进行总体设计，经评审通过后，协调相关模块组长进行概要设计及详细设计的编写及评审，产品经理根据要求进行原型设计，评审通过后交至QA。QA与测试沟通进行测试用例、测试计划的编写。
###7. 实施进度计划
产品经理向各组负责人阐述产品需求及工期要求，组长估算工作量后指派工程师到该产品线工作。产品经理整理实施进度计划表（**<font color = #B22222>模板</font>**）（详细到功能，注意任务拆解不能将整体模块分配给一个人做），评审通过后交至QA。
###8. 分配任务
QA根据各项文档，对应实施进度计划，建立需求跟踪表以便使功能模块设计、测试用例设计、任务与需求相互对应。根据需求编号建立系统任务并分派至人。
###9. 研发实施
产品经理负责产品研发进度及各分派至本产品线工程师的工作安排，组长负责解决本组工程师在工作中遇到的困难并对本组工程师的工作成果的质量负责。架构师负责把关所有代码。

代码编写完成后经过员工自检、组内互检、组长检查后提交git并流转本任务至测试组，由测试组测试通过后流转至QA确认任务关闭。

架构师全程监控代码质量有**<font color = #B22222>一票否决权，可以要求工程师重新编写</font>**。

开发过程中的文档、会议记录均需提交QA统一管理。
###10. 任务变更
开发过程中的需求变化及由于需求增加或减少而产生的新模块、功能、时间变化等，经会议讨论评审后，由产品经理填写**<font color = #B22222>变更表（模板）</font>**交QA，QA根据变更表进行系统任务修改。
###11. 产品测试
子系统开发完成后，整体移交测试组进行测试，回归测试结束后，测试组提交测试计划、测试用例、测试报告、缺陷管理表、验收报告等相关文件至QA。
###12. 文档编写
全部工作完成后，架构师组织进行用户手册、安装部署手册编写工作，并总结本次研发，提交技术总结至QA。
###13. 工作的评审及归档
<br>
<img src="/Users/shou/Desktop/4.jpg" width= 550 height=700 />
<br>
<br>


# Git 学习笔记

[GitHub](https://github.com/gisok/git-study.git)

[TOC]

## 操作命令

### 创建文本地文件夹

### status:查看状态

```
git status
```

### init:初始化该文件夹为GIT仓库

```
    git init
```

所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外.

Microsoft的Word格式是二进制格式，因此，版本控制系统是没法跟踪Word文件的改动的.

强烈建议使用标准的UTF-8编码，所有语言使用同一种编码，既没有冲突，又被所有平台所支持
千万不要使用Windows自带的记事本编辑任何文本文件。原因是保存UTF-8编码文件时在每个文件开头添加了0xefbbbf（十六进制）字符。

### add:把文件添加到仓库
建立或拷贝文件到文件夹
执行 GIT add
```
git add readme.txt
```

提交所有文件

```
git add ./*
```

### commit:把文件提交到仓库
建立或拷贝文件到文件夹
执行 GIT add
```
git commit -m "提交第一个文件 readme.txt"
```

commit可以一次提交很多文件


### diff:查看文件有什么改动

```
git diff readme.txt
```

### log：查看版本记录

```
git log
```


### reset:设置当前版本

* 当前版本标记为 HEAD,上一个版本为 HEAD^,上上一个为 HEAD^^, 上上上一个为 HEAD~3

```
git reset --hard HEAD^
```

* 根据版本号设定回到哪个版本

```
git reset --hard bcc91a
```


### reflog：查看版本设定记录

```
git reflog
```

### checkout -- ：单个文件撤销修改
* 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

* 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

* 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。


### rm：删除版本库中的文件

```
git rm readme.txt
```

### remote add : 关联远程库

```
$ git remote add origin git@github.com:michaelliao/learngit.git
```

### push : 推送本地库到远程库

```
git push -u origin master
```

由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

从现在起，只要本地作了提交，就可以通过命令：

```
$ git push origin master
```

把本地master分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！

### branch: 查看分支

```
$ git branch
```


### branch 分支名: 创建分支

```
$ git branch dev
```


### checkout -b : 创建并切换分支

```
$ git checkout -b dev
```

### clone : 从github克隆项目

```
$ git clone git@github.com:michaelliao/gitskills.git
```

### 删除GitHub仓库

![删除GitHub仓库1](http://images2015.cnblogs.com/blog/856299/201611/856299-20161108232442249-459290234.jpg)


![删除GitHub仓库2](http://images2015.cnblogs.com/blog/856299/201611/856299-20161108232452280-1027780882.jpg)

## 概念

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
    
## 注意

### 文件名大小写敏感


## 遇到的问题

### 怎么使用汉字文件名?

通过将Git配置变量 core.quotepath 设置为false，就可以解决中文文件名称在这些Git命令输出中的显示问题，

```        
$ git config --global core.quotepath false
$ git status -s
?? 说明.txt
```


### 错误提示：fatal: remote origin already exists.  

如果输入$ git remote add origin git@github.com:djqiang（github帐号名）/gitdemo（项目名）.git 
提示出错信息：fatal: remote origin already exists.
解决办法如下：

1. 先输入$ git remote rm origin
2. 再输入$ git remote add origin git@github.com:djqiang/gitdemo.git 就不会报错了！
3. 如果输入$ git remote rm origin 还是报错的话，error: Could not remove config section 'remote.origin'. 我们需要修改gitconfig文件的内容
4. 找到你的github的安装路径，我的是C:\Users\ASUS\AppData\Local\GitHub\PortableGit_ca477551eeb4aea0e4ae9fcd3358bd96720bb5c8\etc
5. 找到一个名为gitconfig的文件，打开它把里面的[remote "origin"]那一行删掉就好了！

