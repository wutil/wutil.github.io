title: linux   strace命令
date: 2015-01-29 14:43:03
categories: linux
tags: [命令,工具]
---
追踪php
---
{% codeblock lang:cpp %}
[root@centos html]# strace -c php test.php 
ok,选择数据库成功！% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
 21.80    0.011022          16       704           read
 16.92    0.008556          33       258        30 open
 11.78    0.005958          25       239           close
  8.30    0.004198          18       231           munmap
  7.77    0.003931          10       404           mmap
  6.29    0.003181          12       268           fstat
  4.40    0.002223          45        49        38 ioctl
  3.96    0.002000        2000         1           execve
  3.90    0.001972          14       143           mprotect
  3.56    0.001800          25        71        15 stat
  1.98    0.001000         125         8           poll
  1.98    0.001000        1000         1           shutdown
  1.89    0.000958          74        13         2 futex
  1.20    0.000607          76         8           rt_sigaction
  1.17    0.000591          12        48         3 lseek
  1.06    0.000538          54        10           fcntl
  0.68    0.000343         343         1           getsockopt
  0.36    0.000184          31         6         5 connect
  0.31    0.000155          39         4           getdents
  0.26    0.000132           4        31           brk
  0.24    0.000123          31         4           sendto
  0.18    0.000093          47         2           statfs
  0.00    0.000000           0         4           write
  0.00    0.000000           0        17         8 lstat
  0.00    0.000000           0         6           rt_sigprocmask
  0.00    0.000000           0         5         3 access
  0.00    0.000000           0         3           alarm
  0.00    0.000000           0         8           socket
  0.00    0.000000           0         2           recvfrom
  0.00    0.000000           0         6           recvmsg
  0.00    0.000000           0         2           bind
  0.00    0.000000           0         2           getsockname
  0.00    0.000000           0         5           setsockopt
  0.00    0.000000           0         1           clone
  0.00    0.000000           0         2           uname
  0.00    0.000000           0         3           getcwd
  0.00    0.000000           0         1           getrlimit
  0.00    0.000000           0         3           times
  0.00    0.000000           0         1           getuid
  0.00    0.000000           0         1           arch_prctl
  0.00    0.000000           0         1           gettid
  0.00    0.000000           0         1           set_tid_address
  0.00    0.000000           0         1           set_robust_list
------ ----------- ----------- --------- --------- ----------------
100.00    0.050565                  2579       104 total
{% endcodeblock %}

参考网站
---
(linux   strace命令详解  进程跟踪 )[http://blog.sina.com.cn/s/blog_6e07f1eb0100t7rg.html]


