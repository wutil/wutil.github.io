---
title: 转战hexo
date: 2015-01-23 13:43:11
categories: web
tags: hexo
---
为什么用hexo
---
因为[hexo](http://hexo.io/ "hexo")比较符合我的审美标准，也许作者是台湾的原因吧。
  一个坑，备份的时候，没有备份pacman theme,最后发现需要删除 .git
if you want to back up with your theme,just add theme: your theme name in _config.yml.
{% codeblock lang:cpp %}
backup:
    type: git
    theme: pacman
    repository:
       github: git@github.com:xxx/xxx.git,branchName
       gitcafe: git@github.com:xxx/xxx.git,branchName
Attention: if you do as above, the dir themes/pacman/.gitwill be removed
再备份也需要删除 根目录.git
{% endcodeblock %}


命令
---
常用命令
{% codeblock lang:cpp %}
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #将.deploy目录部署到GitHub
{% endcodeblock %}
常用复合命令：
{% codeblock lang:cpp %}
hexo deploy -g
hexo server -g
{% endcodeblock %}
简写
{% codeblock lang:cpp %}
hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
{% endcodeblock %}

常见问题
---
{% codeblock lang:cpp %}
删除右边错误的标签
保险起见 删除db.json 删除 source下 tags下的相应标签
多个标签 [1,2,3....]
{% endcodeblock %}

参考网站
---
[hexo你的博客](http://ibruce.info/2013/11/22/hexo-your-blog/)
