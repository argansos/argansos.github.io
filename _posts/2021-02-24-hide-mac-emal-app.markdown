---
layout:     post
title:      "解决 MacOS 上 mail.app 自动弹出的一种办法"
subtitle:   "A step-by-setp setup instructions"
date:       2021-02-24 18:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - mac
    - mail
---

<code style="color:red">转载</code>

##### 解决方法

1.  > System Preference > Keyboard > Shortcuts > App shortcuts

2. 点击加号添加一个新的选项

3.  输入配置如下：
> Application: Mail.app // 列表中手动选择<br />
> Menu Title: Hide Mail // mail中顶栏菜单中的实际操作名称<br />
> Keyboard Shortcut: ⌘W // 直接在键盘使用command+W就可以设定了

4.  点击add

5.  关闭 System Preference

6.  重新启动 Mail.app

现在就能开心的使用command+W来“关闭”mail的窗口也不会被“半屏”打扰到啦~

##### Reference
* [Case of Xeon's post](https://hexo.chensmallx.top/2019/10/25/solve-mac-mail-pop-up-bug/#0x00-发现问题)
