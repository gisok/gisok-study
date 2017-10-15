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

## reset:设置当前版本

当前版本标记为 HEAD,上一个版本为 HEAD^,上上一个为 HEAD^^, 上上上一个为 HEAD~3

```
git reset --hard HEAD^
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
