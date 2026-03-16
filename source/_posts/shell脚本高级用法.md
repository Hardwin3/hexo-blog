---
title: "shell脚本高级用法"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

# shell脚本高级用法

#### 循环执行

- for

- while

- until

- 循环控制语句



continue,提前结束本轮循环

- break,结束循环



- while特殊用法：遍历文件的行



```shell
while read VAR;do
循环体；
done 

#### 控制语句

- 多分支if,执行到一个结束就不执行了



```shell
if condtion1;then
...
elif condition2;then
...
elif condition3;then
...
else
...
fi
```

- case语句



```shell
case $VAR in
PAT1)
分支1
;;
PAT2)
分支2
;;
PAT3)
分支3
;;
*)
分支4
;;
esac
```
