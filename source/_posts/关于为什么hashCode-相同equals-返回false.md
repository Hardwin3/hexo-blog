---
title: "关于为什么hashCode()相同equals()返回false"
date: 2024-02-19 09:02:46
categories:
  - 学习
  - 面试
tags:
  - java
---

---


---


### 前言
在学习hashCode()的时候发现hashCode（）值相同，两个对象返回的equals也不一定相同，这里的equals（）关注的是内容的比较。



```java
String str1 = "适量";
String str2 = "通话";
System.out.println(String.format("str1：%d | str2：%d",str1.hashCode(),str2.hashCode());
System.out.println(str1.equals(str2));
```


执行结果发现hashCode()返回值相同，equals()返回的却是false,因为hash值相同并不能确定两个对象在内容上是相同的。hash是一种单向密码体制，即它是一个从明文到密文的不可逆的映射，只有加密过程，没有解密过程。同时，哈希函数可以将任意长度的输入经过变化以后得到固定长度的输出。哈希函数的这种单向特征和输出数据长度固定的特征使得它可以生成消息或者数据。
