title: yum 安装出错 skip-broken
date: 2015-01-29 11:17:02
categories: linux
tags: [linux,yum]
---
安装依赖包出错
---
  提示 
  {% codeblock lang:cpp %}
  You could try using --skip-broken to work around the problem
  You could try running: rpm -Va --nofiles --nodigest
  {% endcodeblock %}
  
  安装的依赖包和现有的冲突，不能发现新的包
  
  
解决办法
---
  {% codeblock lang:cpp %}
  rpm -e --allmatches --nodeps pcre
  --allmatches
    删除所有那些包匹配PACKAGE_NAME的版本。如果PACKAGE_NAME有多个匹配，正常情况下将有一个错误说明。
  --nodeps
     在没有安装包之前，不检测依赖关系。
  {% endcodeblock %}
  强制删除所有的包，然后安装新的依赖。问题解决。
  网上有人说，如果对删除包，再安装也许会对之前依赖相关包的软件有影响，所以谨慎操作。

其他方法
---
   {% codeblock lang:cpp %}
   原因：多个库共存冲突   
   在执行命令后面加上：
   --setopt=protected_multilib=false 
   {% endcodeblock %}
   未曾尝试，不过也有上述的隐患。
   
   
