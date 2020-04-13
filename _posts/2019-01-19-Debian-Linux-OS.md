---
layout: post
title:  "搭建Debian系统及配置"
date:   2019-01-19 15:03
categories: Linux
tags: Linux Debian
---

* content
{:toc}

主要总结Debian9操作系统在搭建过程中所遇到的坑以及各种配置问题



## 搭建过程

使用VMware来搭建虚拟机

搭建的是Debian Live版本

具体流程参考以下链接：

 [https://jingyan.baidu.com/article/4d58d541791ffb9dd4e9c0e5.html]( https://jingyan.baidu.com/article/4d58d541791ffb9dd4e9c0e5.html)


## 配置


### 使debian系统的界面铺满整个屏幕

1 安装vmware tools工具

vmware workstation -> Install VMware Tools... -> Install

![](https://screenshotscdn.firefoxusercontent.com/images/d0dc1c96-d8f1-4365-9de2-0f7f235c56f3.png)

![](https://screenshotscdn.firefoxusercontent.com/images/45290429-382f-4cd5-a635-7ba700a8b5d8.png)

2 在屏幕上会出现虚拟的光盘，我们双击打开之后将vmware tools压缩包复制到桌面上

![](https://screenshotscdn.firefoxusercontent.com/images/5e2d913f-57d4-4c6a-8412-d1ee0cd22052.png)

![](https://screenshotscdn.firefoxusercontent.com/images/221eb29c-9f89-475a-ba3d-1bcdfe05c0c3.png)

3 打开终端，切换至桌面目录

解压工具包，解压完成后，使用root权限执行里面的工具

![](https://screenshotscdn.firefoxusercontent.com/images/9dceea17-44ff-4472-89b1-566c2362b47b.png)

![](https://screenshotscdn.firefoxusercontent.com/images/4fffd7c4-2062-46f9-9f32-b27bcdfcf4d6.png)

### 设置终端颜色

（1）终端背景颜色：

     终端 -- 编辑 -- 配置文件首选项 -- 颜色

（2）自定义终端字体颜色：

     1 修改终端配置文件：getit ~/.bashrc

     2 文件末尾加入代码：

     PS1='${debian_chroot:+($debian_chroot)}\[\033[01;33;1m\]\u\[\033[00;32;1m\]@\[\033[01;36;1m\]\h\[\033[00;32;1m\]:\[\033[00;34;1m\]\w \[\033[01;32;1m\]\$ \[\033[01;37;1m\]'

     3 保存后执行更改： source .bashrc

自定义颜色：
     
![](https://screenshotscdn.firefoxusercontent.com/images/94ff8af5-0f46-4be4-a8c4-93eb9c42922e.png)

![](https://screenshotscdn.firefoxusercontent.com/images/2efc8210-5bda-413b-9ab6-b3e7bf7668ed.png)

设置语法：

    \u@\h:\w\$表示：用户名@主机名:路径名$

    每一个形如\033[01;33;1m]的结点设置了一项的颜色，表示为：\033[代码;前景;背景m],可在前文表格中自选设定

### Debian9 下截图

命令行下运行：gnome-screenshot  -a ，图片保存在用户目录图片文件夹下；

运行man gnome-screenshot ，可查看更多选项


