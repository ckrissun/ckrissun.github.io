---
layout: post
title: "Mac: Build MacVim"
date: 2013-07-05 20:50
category: "工具"
tags: [Mac 工具]
---

{% include JB/setup %}


Github源码

      git clone https://github.com/b4winckler/macvim.git

Build

      CC=clang ./configure --with-features=huge \
                           --enable-rubyinterp \
                           --enable-pythoninterp \
                           --enable-perlinterp \
                           --enable-cscope
      make

Install

      cp -a src/MacVim/build/Release/MacVim.app ~/Applications/MacVim.app

Configure:

      git clone https://github.com/amix/vimrc.git

      and have a look at here (https://github.com/amix/vimrc)


Have fun, thanks!


### TO-DO
+ Build MacVim 
