---
layout: post
title: "Mac: 安装Jekyll博客系统"
date: 2013-06-29 16:56
category: Tool
tags: [Mac, Tool]
---
{% include JB/setup %}


部署Jekyll时，需要使用Ruby 1.9.x以上，而最新的Mac OSX 10.8.x系统上使用Ruby 1.8.x，需要使用RVM来安装不同的Ruby版本。

也可以使用homebrew安装ruby，有兴趣的朋友可以尝试。

    brew install ruby


### 安装RVM
---
RVM被用来管理系统中不同的Ruby版本，安装前请对RVM[进行了解](https://rvm.io/rvm/install/)。

安装稳定版

	curl -L https://get.rvm.io | bash -s stable

安装过程中输出的信息，会提示如何启用rvm，如使用

	source ~/.rvm/scripts/rvm
	
即可使用RVM。

安装成功后，在~/.bash_profile中会自动添加

	[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
	
表示在打开终端时自动加载

为了加快RVM下载源码的速度，可以修改RVM的源码镜像地址，具体请参考[RubyGems淘宝镜像](http://ruby.taobao.org)

### 安装Ruby
---
通过RVM中安装Ruby 2.0.0
    
    rvm install 2.0.0

安装过程中，若下载Ruby 2.0.0源码时较慢或者没有反应，可以手动[下载Ruby 2.0.0](http://ftp.ruby-lang.org/pub/ruby/2.0)。然后把Ruby源码放在~/.rvm/archives/目录下，重新执行安装即可。

    rvm reinstall 2.0.0

启用Ruby 2.0.0

    rvm use 2.0.0
    
使用Rubygems安装包时，为了加快下载速度，可以改用RubyGems淘宝镜像，具体设置请参考[RubyGems淘宝镜像](http://ruby.taobao.org)

###安装 Jekyll
---
通过RubyGems安装

    gem install jekyll jekyll-tagging

如果不需要用默认的Markdown模版Maruku，想使用RDiscount，则请安装：    
    
    gem install rdiscount
    
### TO-DO
---
+ github环境搭建
+ jekyll配置

### Refrence
---
+ [在Mac中部署你的Jekyll](http://equation85.github.io/blog/install-jekyll-on-mac/)
+ [Installing-Jekyll-on-Mac](http://brandonbohling.com/2011/08/27/Installing-Jekyll-on-Mac/)
+ [Blogging with Jekyll Tutorial | Jekyll-Bootstrap](http://jekyllbootstrap.com)
