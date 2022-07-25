---
title: chown-chgrp
date: 2021-04-13 21:55:07
tags: [ubuntu, chown, chgrp]
categories: ubuntu  
description: 更改文件所属者
---

**reference**: https://www.cnblogs.com/wanglijun/p/8657809.html

## 更改文件属性

1. chgrp：更改文件属组
   
    语法：
   
    chgrp [-R] 属组名文件名
   
    参数选项
   
    -R：递归更改文件属组，就是在更改某个目录文件的属组时，如果加上-R的参数，那么该目录下的所有文件的属组都会更改。
   
     如: 
   
    chgrp -R daokr test  更改 test的 目录属于组daokr  但是daokr用户无法修改该目录文件

2. chown：更改文件属主，也可以同时更改文件属组
   
    语法：
   
    chown [–R] 属主名 文件名
    chown [-R] 属主名：属组名 文件名
