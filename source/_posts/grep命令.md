---
title: "grep命令"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

# grep命令

#### 三剑客

- grep 文本过滤工具

- sed sream editor,流编辑器，文本编辑工具

- awk 文本报告生成器，格式化文本



#### 正则表达式
表示控制或通配的功能的特殊字符



- 基本正则表达式 BRE

- 拓展正则表达式 ERE

- Notes



#### grep:Global search ERgular expression and Print out the line(输出的是行)

- 文本搜索工具，根据用户指定的“模式”，对目标文本进行匹配检查，打印匹配到的行

- 模式：由正则表达式的元字符及文本字符所编写的过滤条件

- 格式：



grep [options] Pattern [file]

- grep [OPTIONS] -e PATTERN … [FILE…]

- grep [OPTIONS] -f FILE … [FILE…]

- OPTIONS:



–color=auto 文本着色

- -I ： Ignore 忽略大小写

- -O：只显示匹配到的文本

- -V ：反向匹配

- -E ：支持拓展的正则表达式

- -Q：–quiet 不输出任何信息

- -A#，-B#，-C#，输出上下的行，A后，B前，C前后



- 基本正则表达式的元字符



字符匹配



. 匹配任意单个字符

- 分组符号（括号）



```plaintext
- 引用，分组括号中的模式匹配到的内容会被正则表达式自动记录下内部变量中
- \1，从左侧起，第一个括号匹配到的字符
- \2
- \3
- 等等
- ```
grep "\(l..e\).*\1" lovers.ext 这样就可以保证同一行中前后出现的一样。
```
