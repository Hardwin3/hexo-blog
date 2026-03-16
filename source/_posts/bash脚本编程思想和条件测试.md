---
title: "bash脚本编程思想和条件测试"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

# bash脚本编程思想和条件测试

- 数据类型



字符型

- 数值型



- 算术运算



```plaintext
+,-,*,/,**
```



let VAR=expression

- VAR=$[expression]

- VAR=$((expression))

- VAR=$(expr argu1 argu2)



- 增强型赋值



`+=，-=，*=，/=,%=

```plaintext
- 要用let 描述， let i+=#
- let VAR++
- 条件测试
- 判断需求是否满足，需要由测试机制来实现
- 如何编写测试表达式以实现所需测试
- 执行命令，并利用命令状态返回值来判断
- 0成功
- 1失败
- 测试表达式
- test expression
- [ expression ]必须有空格
- [[ expression ]]----关键字
- 数值测试：数值比较
- -eq : 是否等于 $num1 -eq $num2
- -ne : 不等于
- -gt :是否大于
- -ge : 是否大于等于
- -lt：是否小于
- -le: 是否小于等于
- 字符串设置：
- ==：等值比较符号
- ```
>:是否大于，外边尽可能使用双括号
```


- ```

- 文件测试



-a 或-e FILE，[-e FILE],是否存在

- -b,是否存在且为块设备

- -c,是否存在且为 字符设备文件

- -d,目录文件

- -f ,普通文件

- -h ,符号连接文件

- -p 命名管道文件

- -S,套接字文件

- 权限测试
-r,是否存在并且当前用户可读

- -w,可写

- -x,可执行



- 特殊权限测试
-g,存在并且拥有suld权限

- -u,是否存在且拥有sgld权限

- -k,sticky权限



- 内容测试
-s,是否为空，空为假



- 时间戳测试
-N，上次读取后是否被修改过



- 从属关系测试
-Q，当前文件是否是文件的属主

- -G,当前用户胡是否为文件的属组



- 双目测试
FILE1－ef FILE2 , FILE2和FILE2是否指向统一文件系统的相同Inode的硬链接

- FILE1 -nt FILE2,FILE1是否新与FILE 2

- FILE1 -ot FILE2,FILE1是否旧与FILE 2



- 逻辑运算
&& || ！

- [ EXPRESSION -a EXPRESSION ] 并且

- [ expression -o expression ]







- 脚本的状态返回值：最后执行的命令的返回值



自定义状态返回值，exit[n],n自定义，返回n。shell遇到exit[n]立马终止
