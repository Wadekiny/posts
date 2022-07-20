---
title: case-and-tab
date: 2021-04-13 21:46:55
tags: [ubuntu, shell]
categories: ubuntu 
description: bash忽略大小写，Tab自动补全
---

## 终端忽略大小写

`~/.inputrc`添加：

```
set completion-ignore-case on
```

## Tab自动补全

`/etc/bash.bashrc`, 找到以下代码，取消注释

```
#enable bash completion in interactive shells
#if ! shopt -oq posix; then
#      if [-f  /usr/share/bash-completion/bash_completion ]; then
#          . /usr/share/bash-completion/bash_completion
#      elif [ -f /etc/bash_completion]; then
#           . /etc/bash_completion
#      fi
#fi
```
