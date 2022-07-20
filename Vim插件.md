---
title: Vim插件
mathjax: true
date: 2021-01-02 15:26:58
tags: [vim, ubuntu]
categories: ubuntu 
description: 使用的vim插件汇总
---
# 图标问题
airline的图标需要安装nerd font字体
powerline 可以匹配行高？

# auto-fcitx-vim

- 方法1：装插件
- 方法2：在 `init.vim` 添加代码


**reference**: https://wiki.archlinux.org/index.php/fcitx

```
  "##### auto fcitx  ###########
  let g:input_toggle = 1
  function! fcitx2en()
     let s:input_status = system("fcitx-remote")
     if s:input_status == 2
        let g:input_toggle = 1
        let l:a = system("fcitx-remote -c")
     endif
  endfunction
  
  function! fcitx2zh()
     let s:input_status = system("fcitx-remote")
     if s:input_status != 2 && g:input_toggle == 1
        let l:a = system("fcitx-remote -o")
        let g:input_toggle = 0
     endif
  endfunction
  
  set ttimeoutlen=150
  "退出插入模式
  autocmd insertleave * call fcitx2en()
  "进入插入模式
  autocmd insertenter * call fcitx2zh()
  "##### auto fcitx end ######
  ```
