---
title: ubuntu18.04美化
date: 2020-12-31 19:09:45
tags: [ubuntu, gnome]
categories: ubuntu
description: gnome桌面环境下的美化 (用i3了，已经不用gnome了)
---

## 安装gnome-tweaks：

```
sudo apt update
sudo apt install gnome-tweak-tool  
sudo apt install gnome-shell-extensions
```

gnome-tweak-tool是主要工具，另外可以安装一些其他的扩展

## 美化图标，主题，shell

可以从https://www.pling.com/browse/cat/135/ord/rating
上下载喜欢的主题图标，解压到`/usr/share/icons`
例如：

1. 已经下载下来图标tela
2. 将tela文件夹放到`/usr/share/icons`
3. 终端下`gnome-tweaks`
4. 在apperance->themes->icons选择tela主题图标

主题，shell这些都类似，要自定义shell，需要打开extensions中的User themes。

## 好用的扩展dash to panel

参考了：https://www.cnblogs.com/feipeng8848/p/12808128.html
没有和dash to dock 一起使用，之前用dash to dock 也不觉得有多方便。
而且状态栏放在最上面每次关浏览器还要瞄准那个X


1. 到这里：https://extensions.gnome.org/extension/1160/dash-to-panel/
2. 右边的off点成on，就装上了
3. 然后就可以再gnome-tweaks里找到它了。


## 单独更改Alacritty的图标

感觉alacritty的图标有点丑，怎么说
感觉tela主题的terminal图标就可以

1. 先把tela主题的terminal图标复制到要改的图标所在目录
2. 切换到所在目录
3. 给旧图标备份
4. 改新图标名字

终端下操作：

```
sudo cp /usr/share/icons/tela/scalable/apps/terminal.svg  /usr/share/pixmaps
cd /usr/share/pixmaps
sudo mv com.alacritty.Alacritty.svg com.alacritty.Alacrittybackup.svg
sudo mv terminal.svg com.alacritty.Alacritty2.svg
```

## 动态桌面壁纸livewallpaper

```
sudo add-apt-repository ppa:fyrmir/livewallpaper-daily
sudo apt update
sudo apt install livewallpaper
sudo apt install livewallpaper-config livewallpaper-indicator
```

---

---
