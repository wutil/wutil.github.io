title: php基础问题汇总
date: 2015-01-27 11:26:23
categories: web
tags: php
---
使用remi及epel源升级php
---
  安装remi及epel源
  

 1，下载并安装epel源# 

rpm -iUh http://mirror.bjtu.edu.cn/fedora-epel/6/x86_64/epel-release-6-8.noarch.rpm  
ps:sohu的也可以
http://mirrors.sohu.com/fedora-epel/6/x86_64/epel-release-6-8.noarch.rpm  

 2，下载并安装remi源# 

rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm  



关于epel:如果既想获得 RHEL 的高质量、高性能、高可靠性，又需要方便易用(关键是免费)的软件包更新功能，那么 Fedora Project 推出的 EPEL(Extra Packages for Enterprise Linux)正好适合你。EPEL(http://fedoraproject.org/wiki/EPEL) 是由 Fedora 社区打造，为 RHEL 及衍生发行版如 CentOS、Scientific Linux 等提供高质量软件包的项目

关于remi:remi软件源对旧的fedora版本提供最新的软件支持，也可以为Centos及RHEL提供最新的软件

3，安装php

yum --enablerepo=remi install php php-cli php-mysql php-gd php-imap php-ldap php-odbc php-pear php-xml php-xmlrpc php-mbstring php-mcrypt php-mssql php-snmp php-soap php-tidy php-common php-devel php-fpm

 使用webtatic源升级php
 ---
1，安装webtatic源

rpm -Uvh http://repo.webtatic.com/yum/centos/5/latest.rpm  

关于webtatic：主要供应最新LAMP等软件源, 支持Cent OS5,6 。这个源 Cent OS 5.x 可以选择 php 5.2 或者 php 5.3.
,2，安装php,

yum --enablerepo=webtatic install php php-*   (如yum --enablerepo=webtatic install php php-5.3)

参考网站
---
[CentOS5使用Yum安装PHP5.3的两种方法](http://www.hczm.cn/post/index/id/135)


