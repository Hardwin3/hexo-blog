---
title: "Linux连接"
date: 2024-01-27 19:48:28
categories:
  - 教程
  - 交流
tags:
  - Linux
---

# Linux连接
查看系统是否监听22端口



```shell
ss -tnl
```


查看网卡信息



```shell
ifconfig
或
addr list
或
ip a
```


查看端口是否开启



```shell
iptables -L -n
临时关闭
iptables -F
```



---


#### linux终端类型

- #### 串行端口终端(/dev/ttySn)，利用计算机串口连接的终端设备。

- 伪终端（/dev/pts/#)如mobaxterm里虚拟出来的终端。

- 虚拟终端(/dev/tty#[1-6]

- 物理终端（/dev/console)


查看接口
```shell
tty
```



#### linux交互接口

- Cli接口：


​	[fu@localhost ~]$


​		fu:当前登录的用户


​		localhost：主机名


​		~：当前工作目录，相对路径


​		#：命令提示符，#为管理员账号，为root，$表示普通用户



#### Linux哲学思想

- 一切皆文件，几乎所有资源都抽象成文件

- 由众多单一的程序组成

- 进行避免和用户进行交互，以编程的方式实现

- 使用文本文件保存配置信息



#### 文件系统

- 层级结构,

- 倒置树状结构
