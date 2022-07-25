---
title: ubuntu18.04 CapsLock和Esc互换
date: 2021-02-12 14:30:35
tags: [ubuntu, vim]
categories: ubuntu 
description: 互换ESC和CapsLock，方便使用vim
---

两种方法：
在使用过程中，先试了第一种，发现系统不会自动运行.Xmodmap的内容，需要自己设置。然后试dconf的方法，可以正常使用。后来装上fcitx输入法后，发现失效了，可能是fcitx又调用了.Xmodmap，把.Xmodmap的名字改掉后就可以正常互换了。

#### 使用xmodmap

安装xmodmap 

`vim ~/.Xmodmap`

添加：

```
clear Lock  
keysym Caps_Lock = Escape  
keysym Escape = Caps_Lock  
add Lock = Caps_Lock  
```

`xmodmap .Xmodmap`

但是这种方法需要设置开机运行xmodmap .Xmodmap

#### 使用dconf

`sudo apt install dconf-editor`
`dconf-editor`

路径：`org / gnome / desktop / input-sources / xkb-options`
把custome value的内容改为：`'caps:swapescape'`
![avatar](./ubuntu18-04-CapsLock和Esc互换/ce.png)
