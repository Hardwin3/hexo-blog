---
title: "java中的==和equals"
date: 2024-02-18 16:08:21
categories:
  - 学习
  - 面试
tags:
  - java


---


### 前言
准备面试时候的记录



#### 使用 == 比较
Java中的8种基本数据类型（byte,short,char,int,long,float,double,boolean）比较他们之间的值是否相等。引用数据类型，比较的是他们在堆内存地址是否相等。每新new一个引用类型的对象，会重新分配堆内存空间，使用==比较返回false。



#### 使用 equals 比较
equals方法是Object类的一个方法，Java当中所有的类都是继承于Object这个超类。JDK1.8 Object类equals方法源码如下，即返回结果取决于两个对象的使用==判断结果。



```java
public boolean equals(Object obj) {
return (this == obj);
}
```



##### 需要注意的例子

```java
String s1 = "abc";
String s2 = "abc";
System.out.println(s1 == s2);
```


返回的是true,因为在”abc”在第一次赋值的时候就存在了变量池中，所以在第二次“abc”被赋值给s2的时候，直接将s2指向了“abc”的同一内存地址。所以返回true。



#### 参考文章
== 和 equals 的区别_==和equals的区别-CSDN博客


java中equals以及==的用法(简单介绍) - 韦邦杠 - 博客园 (cnblogs.com)
