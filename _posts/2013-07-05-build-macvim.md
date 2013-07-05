---
layout: post
title: "Build MacVim"
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

END ...

### TO-DO
+ Build MacVim 
