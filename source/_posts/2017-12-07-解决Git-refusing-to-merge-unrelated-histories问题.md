---
title: 解决Git refusing to merge unrelated histories问题
date: 2017-12-07 15:59:20
copyright: true
categories: git
tags:
- merge 
- histories 
- git
---
![](http://ov4nwwjdl.bkt.clouddn.com/17-12-7/31184667.jpg)
<!--more-->

hexo在github中，我创建了两个远端分支，master为hexo的deploy指向分支，而本身代码分支我保存到dev分支。

当我 `hexo devlop`成功之后，我再将源码提交到dev分支的时候报错：

`
git pull 

fatal: refusing to merge unrelated histories
`

> 查询网上资料后，GIt从版本`2.9.0`开始，预设行为不允许合并没有共同祖先的分支，需要加上`--allow-unrelated-histories`选项进行pull操作


最后解决办法为：

`git pull  --allow-unrelated-histories`