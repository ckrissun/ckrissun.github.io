---
layout: post
title: "Linux: 安装WireShark问题"
date: 2012-11-26 14:39
category: "工具"
tags: [Linux 工具]
---
{% include JB/setup %}


由于项目需要调试网络数据帧，一个开源的好工具是wireshark。在Debian系统下安装wireshark（具体怎么安装就不介绍了）后，打开wireshark文件发现，没有一个网络接口可供操作的，这是肿么回事？

在linux终端下尝试使用sudo来运行wireshark，这才发现，wireshark需要根用户权限才能使用。但话说回来，每次使用这wireshark工具，都用在终端下敲下

    sudo wireshark 

着实有些麻烦，本人一向比较懒，直接点击wireshark图标打开文件，岂不快哉？
在google大神的帮助下，终于找到解决方案:

参考网址: [http://ask.wireshark.org/questions/7976/wireshark-setup-linux-for-nonroot-user](http://ask.wireshark.org/questions/7976/wireshark-setup-linux-for-nonroot-user)

    $ sudo dpkg-reconfigure wireshark-common   
    $ sudo usermod -a -G wireshark $USER  
    $ gnome-session-quit --logout --no-prompt


### TO-DO
---
+ Linux: 安装Wireshark问题
