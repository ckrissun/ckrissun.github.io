---
layout: post
title: "MySQL: 两个实用的时间戳函数"
date: 2013-07-05 19:50
category: "MySQL"
tags: [MySQL]
---

{% include JB/setup %}


1. 时间戳->日期字符串

    SELECT FROM_UNIXTIME(`1373025189`);

2. 日期字符串->时间戳

    SELECT UNIX_TIMESTAMP('2013-07-05 12:00:00');


### TO-DO
+ MySQL: 两个实用的时间戳函数
