---
layout: post
title: "Linux: 使用RT-Thread构建嵌入式应用"
date: 2012-11-26 14:19
category: "嵌入式"
tags: [嵌入式 RTOS]
---
{% include JB/setup %}


本文主要介绍如何在Linux环境使用国人开发的嵌入式实时操作系统RT-Thread构建嵌入式应用。

### 主要环境配置
---
+ 主机系统：Debian wheezy 32bit
+ 交叉编译工具：sourcery g++ lite-2012.09
+ 项目构建工具：scons
+ RT-Thread版本：RT-Thread V1.0.3
+ 开发板：自制STM32F103ZET6开发板 
+ 调试器：JLink

### 工程构建说明
---
在自制的STM32F103ZET6开发板上，基于RT-Thread自带的BSP—stm32f10x构建一个示例工程test，本工程仅仅是一个示例，意在介绍如何在Linux环境使用RT-Thread以及scons构建工具建立嵌入式应用，开发实际项目进行相应修改及扩展即可。

将RT-Thread源码解压到工程目录test中;

在test工程目录中建立应用程序目录apps，此时test工程目录是:
    + apps
    + bsp
    + componets
    + documents
    + examples
    + include
    + libcpu
    + src
    + tools
在apps目录中建立test.c文件，在其中添加代码（假定是一个流水灯的任务代码）后保存;

RT-Thread使用scons工具来进行项目工程构建，RT-Thread中scons的使用可以参照[《RT-Thread中的SCons使用详解》](http://www.rt-thread.org/dokuwiki/doku.php?id=rt-thread中的scons使用详解)，本文不做介绍。需要在apps目录下建立scons编译脚本文件SConscript（实际上是一段Python程序），告诉scons需要编译哪些文件。示例中apps目录下仅有一个文件test.c，因此SConscript文件内容如下:

    Import('RTT_ROOT')
    from building import *

    src = Split("""
    test.c
    """)

    #The set of source files associated with this SConscript file.
    path = [GetCurrentDir()]
    group = DefineGroup('Apps', src, depend = [''], CPPPATH = path)
    Return('group')

在linux终端中，进入到目录bsp/stm32f10x中，执行scons，完成后发现apps目录中的文件并没有编译;

为了能够编译apps目录下的内容，需要修改bsp/stm32f10x目录中的SConstruct文件，在适当的位置添加如下内容:

    #Application
    objs = objs + SConscript(RTT_ROOT + '/apps/SConscript', variant_dir='build/apps', duplicate=0)

这句脚本告诉scons，编译apps目录下的代码并添加到二进制目标文件中，且由apps目录下的SConscript指定编译哪些文件;

再次执行scons，这时候可以看到，apps目录的代码已经被编译;
说明：若要查看apps下的代码有没有被编译，可以查看bsp/stm32f10x/build目录下，有没有apps目录，以及该目录有没有相应的.o文件;

代码烧录到开发板中，操作说明请参照[《Linux下通过Jlink烧写RT-Thread》](http://www.rt-thread.org/dokuwiki/doku.php?id=linux下通过jlink烧写rt-thread)

如何使用scons构建工程项目，请参照[《RT-Thread中的SCons使用详解》](http://www.rt-thread.org/dokuwiki/doku.php?id=rt-thread中的scons使用详解)以及[scons官方文档](http://www.scons.org/documentation.php)。

### TO-DO
---
+ Linux: 使用RT-Thread构建嵌入式应用

