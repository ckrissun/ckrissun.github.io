---
layout: post
title: "Linux: 设置Oracle JDK环境"
date: 2012-11-26 14:54
category: "工具"
tags: [Linux 工具]
---
{% include JB/setup %}


安装好Oracle JDK环境后（实际上是安装到一个目录中），但Linux系统并不知道，需要进行设置，如下：

    $ sudo update-alternatives --install "/usr/bin/java" "java" "/home/sfh/software/jdk1.6.0_37/bin/java" 1  
    $ sudo update-alternatives --install "/usr/bin/javac" "javac" "/home/sfh/software/jdk1.6.0_37/bin/javac" 1  
    $ sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/home/sfh/software/jdk1.6.0_37/bin/javaws" 1  
  
    $ sudo update-alternatives --config java  
    $ sudo update-alternatives --config javac  
    $ sudo update-alternatives --config javaws 

说明：/home/sfh/software/jdk1.6.0_37是jdk的安装目录

    $ java -version

运行后发现java环境设置成功

其次，设置java环境

编辑/etc/profile文件，添加如下：  
    
    #set java environment  
    export JAVA_HOME=/home/sfh/software/jdk1.6.0_37  
    export CLASSPATH=.:$JAVA_HOME/lib:$JAVA_HOME/jre/lib 

    

### TO-DO
---
+ Linux: 设置Oracle JDK环境
