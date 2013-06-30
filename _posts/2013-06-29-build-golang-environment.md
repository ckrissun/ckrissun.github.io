---
layout: post
title: "Golang开发环境: vim+gocode"
date: 2013-06-29 18:02
category: Tool
tags: [Development]
---
{% include JB/setup %}


### 安装Golang
---
下载[Golang编译器](http://code.google.com/p/go/downloads/list)，解压到某一目录，可以放在/usr/local或者~/bin目录，或者其他自己喜好的目录；

设置Golang环境，我的配置如下(Mac)：

    # Golang settings
    export GOROOT=$HOME/Applications/go
    export GOPATH=$HOME/go
    export GOARCH=amd64
    export GOOS=darwin
    export GOBIN=$GOROOT/bin
    export PATH=.:$GOBIN:$PATH

大家可以参考自己的安装环境做一定的修改。其中，
+ GOROOT - Golang的安装目录
+ GOPATH - Golang第三方库安装位置，用go get xx.xx.xx.xx/xx安装第三方库安装到该目录
+ GOARCH - CPU架构，amd64/386/arm/... 
+ GOOS   - 当前使用的OS，linux/darwin/... 

### 安装Gocode
---
参考[官方的安装方法](https://github.com/nsf/gocode)

    go get -u github.com/nsf/gocode (-u flag for "update")

配置Gocode，命令为gocode set option value

    gocode set propose-buildins true
    gocode set lib-path ~/Projects/go/pkg/darwin_amd64:~/go/pkg/darwin_amd64

其中,

+ propose-buildins: 是否自动提示Go的内置函数、类型和常量，默认false，不提示
+ lib-path: 默认情况下，gocode只会搜索$GOPATH/pkg/$GOOS_$GOARCH和$GOROOT/pkg/$GOOS_$GOARCH目录下的包，当然这个设置就是可以设置我们额外的lib能访问的路径，代码自动完成时需要设置该选项

### 配置Vim

复制$GOROOT/misc/vim目录下内容到~/.vim目录

    make -p ~/.vim
    cp -a $GOROOT/misc/vim ~/.vim

安装gocode的vim脚本

    cd $HOME/go/src/github.com/nsf/gocode/vim (gocode的安装目录下)
    ./update
    
启用 filetype plugin

    filetype plugin on

使用golang的代码自动完成

    Ctrl-x Ctrl-o -- 代码编辑时，打开自动完成
    Ctrl-p -- 代码提示列表

### TO-DO
---
+ 搭建Golang开发环境
