title: "Can't connect to MySQL server"
date: 2015-01-29 11:17:51
categories: mysql
tags: [mysql,selinux]
---
问题
---
wordpress更换服务器后，出现can't connect to MySQL server using '' (13)的错误，
结果是 SELinux 不让 httpd 访问外网，一开始还以为是iptables造成的，关闭之后发现还是不行。
 
原因
---
{% codeblock lang:cpp %}
#getsebool -a | grep httpd
[root@centos]#getsebool -a | grep httpd
allow_httpd_anon_write --> off
allow_httpd_mod_auth_ntlm_winbind --> off
allow_httpd_mod_auth_pam --> off
allow_httpd_sys_script_anon_write --> off
httpd_builtin_scripting --> on
httpd_can_check_spam --> off
httpd_can_network_connect --> off
httpd_can_network_connect_cobbler --> off
httpd_can_network_connect_db --> off
httpd_can_network_memcache --> off
httpd_can_network_relay --> off
httpd_can_sendmail --> off
httpd_dbus_avahi --> on
httpd_enable_cgi --> on
httpd_enable_ftp_server --> off
httpd_enable_homedirs --> off
httpd_execmem --> off
httpd_read_user_content --> off
httpd_setrlimit --> off
httpd_ssi_exec --> off
httpd_tmp_exec --> off
httpd_tty_comm --> on
httpd_unified --> off
httpd_use_cifs --> off
httpd_use_gpg --> off
httpd_use_nfs --> off
{% endcodeblock %}

发现 httpd_can_network_connect_db --> off

解决方案
---
{% codeblock lang:cpp %}
/usr/sbin/setsebool -P httpd_can_network_connect_db on
{% endcodeblock %}
参考网站
---
[Can't connect to MySQL server on 'XXX' (13)](http://blog.sina.com.cn/s/blog_8882a6260101ed0p.html)
