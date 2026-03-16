---
title: "shell脚本编程实现"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

## shell脚本编程实现

#### 根据其编程过程中调用库还是调用外部的程序文件

- shell脚本编程


​	利用系统上的命令及编程组件进行编程

- 完整编程


​	利用库或编程组件进行编程


shell脚本编程：过程式编程，解释运行，依赖于外部程序文件运行



#### 如何写shell脚本

- 第一行顶格写shebang,解释器路径，用于指明解释执行当前脚本的解释器程序文件如



#!/bin/bash

- #!/usr/bin/python

- #!/usr/bin/perl


Notes:


​		所以xx.sh其实是一个文本文件，运行这个文件真正的过程是内核读取了文件前面的内容，并用bash去运行文本里的内容。所以当bash xx.sh时，xx.sh并不需要+x权限。


​		脚本中的空白行和#开头的行都会被忽略，除了shebang.



- 文本编辑器



行编辑器：sed

- 全屏幕编辑器：nano ,vi,vim



- bash的配置文件



profile类：为交互式登录的shell提供配置，交互式：通过某终端输入账号密码登录打开的shell；通过su - username或 su -l username打开的终端；


​	全局：对所有用户都生效；


​			/etc/profile


​			/etc/profile.d/*.sh


​	局部：对单个用户生效


​			~/.bash_profile


​	功用：


​			用于定义环境变脸


​			运行命令或脚本

- bashrc类：为非交互式登录的shell提供配置，非交互式：su username;在图形界面打开的终端；运行脚本的时候的子shell；


​	全局：


​			/etc/bashrc


​	用户个人：


​			~/.bashrc


​	功用：


​			定义本地变量


​			定义命令别名


​	交互式登录shell进程：​				/etc/profile—->>/etc/profile.d/*——->/.bash_proflie——>/.bashrc——>/etc/bashrc


​	非交互的shell:


​				~/.bashrc——>/etc/bashrc——>/etc/profile.d/*


​





- 命令行定义的特性，在当前shell有效

- 配置文件定义的特性，在下一次有效



通过命令行重新定义一次

- 重新加载一次配置文件
source

- .






​
