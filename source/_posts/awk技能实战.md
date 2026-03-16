---
title: "awk技能实战"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

# awk技能实战

#### 数组

- 数组声明  declare -a

- 关联数组声明 declare -A



#### 字符串

- 切片

- 查找替换

- 查找删除

- 变量赋值



#### awk工具
文档报告生成器，格式化文本输出



- 基本用法 awk [options] ‘program’ file



program:   PATTERN{ACTION STATEMENTS}，这里的PATTERN不是正则中的模式，而是内置的模式



ACTION_STATEMENTSb



expressions

- Control statements

- Compound statements

- input statements

- out statements

- print    print item1,item2

- printf 用法print FORMAT,item1,item2



FORMAT必须给出

- printf不会自动换行

- FORMAT中需要为后面的每一个item指明一个格式化符号

- 格式符
%c,显示ASCII码

- %d,%i，显示十进制整数

- %e,%E,科学计数法

- %f,浮点数

- %g,%G,科学计数法或者浮点数显示数值

- %s,显示字符串

- %u,无符号整数

- %%，显示为%自身



- 修饰符
%n.n,比如%15s,表示这个变量用15个位置显示

- -：左对齐 0

- +：显示数值的符号





- 操作符



算符运算操作符
x+y,x-y,x*y,x/y,x%y

- -x,取负





- +x,转化为数值



赋值操作符 =，+=，-=，*=，%=，%=，……=，++，–





- 比较操作符 >,>=,==,等等



模式匹配符



~，左边是否能被右侧匹配

- ！~



- 逻辑 && ||  ！

- 函数调用function_name(arg1,arg2,arg3)

- 条件表达式   判断条件?expression:expression三元表示式

- PATTERN



empty:空模式匹配每一行，不写出来就行

- /regular expression/:能被此处的模式匹配到的

- relation expression ,关系表达式，结果有真有假，结果为真就处理，非0为真。非空字符串表示为真。

- line ranges,行范围/pat1/,/pat2/，不支持直接数字格式

- BEGIN/END,BEGIN尽在开始处理文件中的文本之前执行一次，end仅仅在处理完成之后，命令结束之前执行一次。



```shell
awk -F: &#x27;BEGIN{print "    name       uid  "}{print $1,$3}&#x27; /etc/passwd
```




Notes:输出的item可以是字符串，也可以是数值，当前记录的字段，变量或awk表达式。想要变量替换，变量不能写在引号内



- 变量
内建变量（使用的时候不需要$）
FS，输入时分隔符，默认为空白

- OFS，输出时分隔符，默认为空白字符

- RS，输入的换行符

- ORS，输出时的换行符

- NF，每一行的字段数量

- NR,行数

- FNR，每一个文件进行单独计数

- FILENAME，当前文件名

- ARGC，命令行参数个数

- ARGV，数组，命令行中给定的各个参数



- 自定义变量
变量名一样区分大小写

- 可以在program中直接定义，就是后面的{}，多个就用分号分隔







- options



-F ,指明输入时数据的字段分隔符

- -v: var=value 自定义变量
