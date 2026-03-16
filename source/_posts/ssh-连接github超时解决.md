---
title: "ssh 连接github超时解决"
date: 2024-01-27 22:09:31
categories:
  - 教程
  - 交流
tags:
  - Linux
---

今天更新博客，结果推送仓库的时候发现连不上github,一直报错超时。就顺手记录下解决方法。在C://Users/用户名/.ssh/ 目录下的config(没有就新建)内写下。



```plaintext
Host github.com
HostName ssh.github.com
```


重试，成功。



#### 补充
2024年2月21日发现没有联网也会报这个错。
