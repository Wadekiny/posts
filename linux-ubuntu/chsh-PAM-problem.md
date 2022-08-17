---
title: chsh-PAM-problem
date: 2021-04-04 17:39:55
tags: [ubuntu, shell]
categories: ubuntu  
description: 更换shell为zsh遇到的问题
---

#### 问题：

更换shell遇到的问题

使用命令：

```
sudo chsh -s /bin/zsh
```

提示：

```
[sudo] password for wadekiny:
Password:
chsh: PAM: Authentication failure
```

让我输入了两次密码，然后提示验证失败。后发现去掉`sudo`后直接使用命令，不会出现错误

#### 解决：

1. 直接改`/etc/passwd`文件，找到`:/home/wadekiny:/bin/bash`(因人而异)
2. 直接把bash改为zsh，重启后生效
