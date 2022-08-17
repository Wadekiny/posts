---
title: terminator
mathjax: true
tags: [ubuntu, terminal]
date: 2022-02-27 17:51:07
categories: ubuntu
description: 用 terminator 遇到的一些问题
---

### 在 preferences 取消快捷键的绑定
> https://github.com/gnome-terminator/terminator/issues/423

I don't know if resetting a variable to its default value is possible atm besides deleting the changed bind from the config, but you can unset a keybinding by `double clicking` it then hitting `Backspace`.

无需去 ~/.config/terminator/config 里一个个敲
更改完会自动添加到里面


