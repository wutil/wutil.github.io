---
title: github 搭建 octopress
date: 2015-01-22 21:36:18 +0800 
categories: web
tags:
---


### 网上教程很多，我只说坑 ###
 

- 申请github项目的时候，项目名字必须是username.github.io的样式，最初没发现，郁闷了半天
- 申请了github-page，必须在[https://github.com/settings/emails](https://github.com/settings/emails)，邮件确认，否则无效，会收到很多报错邮件
- win下用网上的办法，问题多多，一怒之下，把win下目录共享到虚拟机上，用Linux提交，问题解决
- Linux下需要安装nodejs，否则报下面的错误，git版本要升级到新版本
  
 > error: The requested URL returned error: 401 Unauthorized while accessing https://github.com/zemo/demo.git/info/refs
 > 
 >fatal: HTTP request failed
 >

**参考文章**
 
[http://www.jianshu.com/p/0ac2ac1a8e45](http://www.jianshu.com/p/0ac2ac1a8e45)

[http://xuhehuan.com/783.html](http://xuhehuan.com/783.html)

[http://www.pchou.info/web-build/2014/07/04/build-github-blog-page-08.html](http://www.pchou.info/web-build/2014/07/04/build-github-blog-page-08.html)

[http://nkcoder.github.io/blog/20140105/github-pages-and-octopress-blog-built/](http://nkcoder.github.io/blog/20140105/github-pages-and-octopress-blog-built/)

[http://www.itzhoulin.com/deploy-a-blog-using-octopress-hosted-in-github/](http://www.itzhoulin.com/deploy-a-blog-using-octopress-hosted-in-github/)

[http://www.tuicool.com/articles/63QfIfv](http://www.tuicool.com/articles/63QfIfv)

