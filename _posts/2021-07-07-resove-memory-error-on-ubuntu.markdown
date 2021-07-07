---
layout:     post
title:      "[FW] MemoryError: Unable to allocate xx MiB for an array with shape ..."
subtitle:   "A step-by-setp setup instructions"
date:       2021-07-07 12:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - python
    - linux
---

##### 错误信息

> MemoryError: Unable to allocate xx MiB for an array with shape ...

##### 系统环境

- Ubuntu 18.04 LTS
- Python 3.8

##### 解决方法

1. 首先检查系统的内存过载处理模式
```bash
$ cat /proc/sys/vm/overcommit_memory
```
不出意外的话结果应该是0

2. 然后切换到 root 用户（否则权限不够）
```bash
$ sudo passwd root
```
然后输入当前用户密码，再给 root 设定一个新密码，再切换到 root：
```bash
$su root
```
你会发现$变成了#
3. 现在我们拥有了 root 权限，输入下面的命令将内存过载处理模式更改为1：
```bash
$ echo 1 > /proc/sys/vm/overcommit_memory
```
然后不出意外的话，就可以成功创建该矩阵啦！

##### Reference
* [Xovee's Blog](https://blog.csdn.net/xovee/article/details/101077022)

