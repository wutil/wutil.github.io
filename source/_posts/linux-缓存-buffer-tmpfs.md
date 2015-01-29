title: linux 缓存 buffer tmpfs
date: 2015-01-26 14:19:46
categories: linux
tags: 内核
---
共享内存
--------
{% codeblock lang:cpp %}
cat /proc/sys/kernel/shmmax  // 定义了共享内存段的最大尺寸（以字节为单位）
68719476736/1024/1024/1024  //64G centos6 X 64 默认
cat /proc/sys/kernel/shmmin  用于设置系统范围内共享内存段的最大数量。该参数的默认值是 4096 。通常不需要更改。（有的说是单个段允许使用的最小共享内存大小 存疑）
4096
cat /proc/sys/kernel/shmall  表示系统一次可以使用的共享内存总量（以页为单位）。（有的说是全部允许使用的共享内存大小，单位是页,可以通过getconf PAGESIZE来获取每页的大小，一般为4096字节 存疑，因为换算后的值还没有MAX的大）
4294967296
ipcs -l 可以查看相关内容
{% endcodeblock %}

/dev/shm
----------------

{% codeblock lang:cpp %}
   /dev/shm是linux非常有用的一个目录，它就是所谓的tmpfs，也可以称之为临时文件系统（不是块设备），类似oracle中的临时表空间一样，用于加速和优化系统。该目录并没有放在磁盘上，而上在内存当中。因此在linux下，不用大费周折的去建ramdisk，直接使用/dev/shm就可以达到很好的效果。
       Tmpfs和ramdisk（虚拟磁盘）。Tmpfs可以使用RAM，也可以使用交换分区来进行存储。传统的ramdisk（虚拟磁盘）是个块设备，并且需要mkfs之类的命令之后才可以真正的使用它。Tmpfs是一个文件系统，不是块设备，系统默认启动就会加载/dev/shm，只要安装它就可以使用了。
       Tmpfs优势。
1.    动态文件系统的大小
2.    读写速度快。典型的tmpfs文件系统会完全驻留在RAM中，读写几乎是瞬间完成。
3.    Tmpfs中的数据在重新启动之后不会保留，因为虚拟内存本质上是易失的，所以有必要做些脚本做诸如加载、绑定的操作。

coreOS 个别目录放在了tmpfs上

{% endcodeblock %}

linux cache and buffer
---------
[linux cache and buffer](http://blog.csdn.net/turkeyzhou/article/details/6426738)

待续，暂存于此

