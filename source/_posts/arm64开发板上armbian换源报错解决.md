---
title: "arm64开发板上armbian换源报错解决"
date: 2024-01-27 19:43:17
---

arm64开发板上armbian换源报错E: 无法下载 [https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/dists/focal/restricted/binary-amd64/Packages](https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/dists/focal/restricted/binary-amd64/Packages)  404  Not Found [IP: 101.6.15.130 443]
##### sources.list如图

![sources.list](/images/posts/sources-list.png)

![apt报错](/images/posts/apt-error.png)

结果 sudo apt update 却遇上了报错




分明使用的是ubuntu-ports,处理器架构也是arm64,apt 怎么会去获取amd64的软件包呢，多次换源无果，实在令人难解。


好在根据关键词多次搜索，终于发现原因所在。使用dpkg查看系统软件包架构发现



```shell
ajin@CRRC:~$ dpkg --print-foreign-architectures
armhf
amd64
```


这一指令可以显示已安装软件包中包含的其他体系架构，比如系统本身是64位的，而用户安装了一个32位的软件，则这个32位的体系结构就被称为”foreign-architectures”.


所以解决方法就是用dpkg来移除这个amd64的额外架构。



```shell
ajin@CRRC:~$ sudo dpkg --remove-architecture amd64
ajin@CRRC:~$ sudo apt update
命中:1 http://mirrors.tuna.tsinghua.edu.cn/armbian focal InRelease
命中:2 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal InRelease
命中:3 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-updates InRelease
命中:4 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-backports InRelease
命中:6 http://ppa.launchpad.net/openjdk-r/ppa/ubuntu focal InRelease
命中:7 http://ports.ubuntu.com/ubuntu-ports focal-security InRelease
命中:5 http://mirrors.ustc.edu.cn/armbian focal InRelease
命中:8 https://download.docker.com/linux/ubuntu focal InRelease
获取:9 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal/universe armhf Packages [10.9 MB]
获取:10 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal/restricted armhf Packages [10.8 kB]
获取:11 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal/main armhf Packages [1,227 kB]
获取:12 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal/multiverse armhf Packages [141 kB]
获取:13 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-updates/multiverse armhf Packages [9,898 B]
获取:14 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-updates/restricted armhf Packages [21.9 kB]
获取:15 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-updates/main armhf Packages [1,835 kB]
获取:16 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-updates/universe armhf Packages [1,172 kB]
获取:17 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-backports/universe armhf Packages [27.8 kB]
获取:18 https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports focal-backports/main armhf Packages [54.7 kB]
获取:19 http://ports.ubuntu.com/ubuntu-ports focal-security/universe armhf Packages [887 kB]
获取:20 http://ports.ubuntu.com/ubuntu-ports focal-security/multiverse armhf Packages [5,099 B]
获取:21 http://ports.ubuntu.com/ubuntu-ports focal-security/main armhf Packages [1,475 kB]
获取:22 http://ports.ubuntu.com/ubuntu-ports focal-security/restricted armhf Packages [21.6 kB]
正在读取软件包列表... 完成
正在分析软件包的依赖关系树
正在读取状态信息... 完成
有 286 个软件包可以升级。请执行 ‘apt list --upgradable’ 来查看它们。
```


之后果然没有报错了。



##### 另外一种解决方法是在/etc/apt/sources.list中去指定自己需要的架构的软件包

```shell
deb [arch=arm64] https://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ focal main restricted universe multiverse
```
