---
title: "BASH特性和bash编程"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

# BASH特性和bash编程

#### bash 的特性

- 命令行展开： ~，{}

- 命令别名：alias,unalias

- 命令历史：history

- 文件名通配：glob

- 快捷键：Ctrl+a,e,u,k,l

- 命令补全

- 路径补全

- 命令hash，缓存之前命令的查找结果，用hash 可以查看

- 变量



```shell
程序：数据+指令
指令：程序文件提供
数据：IO设备，文件，管道，变量
bash是一种弱类型的编程语言，把所有变量视为字符传芳。并且变量无需事先声明。
变量引用:${var_name},$var_name
变量名：包含数字，字母，下划线，同时不能以数字开头。
变量类型：
本地变量：当前shell进程
变量引用:${var_name},$var_name
"":变量名会替换为值
&#x27;&#x27;：变量名不会替换为值
设置或者查看变量：set
撤销：unset var_name(不适用$)
环境变量：当前shell以及子shell
变量赋值：
1.export name=fu
2.name=fu
export name
3.declare -x name=fu
查看环境变量：export,declare -x printenv,env
撤销环境变量:unset var_name
局部变量：某个代码作用域
位置参数变量：向执行脚本的shell进程传递的参数
特殊变量：shell内置的由特殊功能的变量
Notes:
设置为只读变量:readonly var_name或者declare -r var_name.
```



- 多命令执行：        command；command；….按顺序执行

- 逻辑运算：
真（true，yes，on,1)

- 假（false,no,off,0)

- 与 &&

- 或 ||

- 非 ！
