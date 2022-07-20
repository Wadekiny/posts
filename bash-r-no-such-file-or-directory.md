---
title: "报错：bash\r:no such file or directory"
date: 2021-04-13 20:29:25
tags: [ubuntu, shell]
categories: ubuntu 
description: 文件格式导致的错误
---

**reference**: https://www.cnblogs.com/Cqlismy/p/12888768.html

- 提示： `/usr/bin/env: ‘bash\r’: No such file or directory`

- 原因：文件格式

- 解决：
  
  ```
  $ nvim make.sh 
  
  :set ff
  ```
  
    显示：`fileformat=dos`
  
  ```
  :set ff=unix
  :wq
  ```
