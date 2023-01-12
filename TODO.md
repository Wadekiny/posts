---
title: TODO
mathjax: true
tags: [todo]
date: 9000-01-01 22:50:05
categories: todo
description: todo list
---



目的：
恢复更仿真的人脸：

回归3dmm参数生成大致shape和texture
学习text2face的方法，分开面部部件，shape上分开？分开才能精细可控
hair eye

额外的uv图用来恢复高清细节

模型去除光照渲染
反射率之类的东西
部件gcn
meshgcn


粗-细
眼镜


pyright opencv
clash for windows git加速(还是用qv2ray把)
舞蹈和人脸合成一起

纹理细节为什么不好？


无线电 群里的论文
expgan


i3: autotiling
i3: lxappearance

vim: vim-surround (ysiw3*)
vim: startify
vim: lightline, bufferline
vim: coc-explorer
vim: plugin - treesitter- too long 'if,for,class,function...,' 
vim: line tab4 highlight
vim: highlight func class...too long 
vim: pwd at right top
vim: set autochdir 自动改变工作目录
：cd改变工作目录
see more details: `:h expand`

.zshrc
alias todo='nvim ~/BLOG/source/_posts/TODO.md'

coc补全边框圆角显示问题巴拉巴拉，是alacritty的问题，更新最新版的alacritty，就好了

system: asd2123
ranger:select-editor







sogou
nvidia驱动








dwm,i3获取窗口 
xprop
xwininfo
notify-osd
dunst!
dunst要不要加到开机启动？
vim:hex 16进制表示方法
:set laststatus=2
:set statusline=%<%f%h%m%r%=%b\ 0x%B\ \ %l,%c%V\ %P
dwm statusbar 日期部分显示异常，加正则表达式替换
 cal | sed  's/_/test/g' | nvim
：
cal | sed 's/_^H/ /' | sed 's/  _^H/>/'
正则替换每一个可能的清空
dwm statusbar路径设置
vim 正则表达式替换
vim宏+1功能 c-a
ls20东蒙人工智能团支部p
clash for window
wsl代理需要设置防火墙
ip到底是哪个？

easyconnect 打开导致不能git push


proxy打开后，pip install报错 https://blog.csdn.net/tuzixini/article/details/88203910
mason 不能安装python-lanuage-server https://www.saoniuhuo.com/question/detail-2133503.htmlcli

2022-12-23T16:57:49 Warning  WARN Client 1 quit with exit code 1 and signal 0 ,checkhealth,是不是有依赖不匹配


1. kitty and Chinese
2. Xauthority should be wadekiny's, instaed, login loop
3. Nvidia driver should be 470.xxx. or black screen
4. a lot of nvim stateline
5. i3-gaps
6. fcitx
7. ranger kitty preview image
8. i3 picom ,is updating
9. betterlockscreen  need i3lock ..
10. git speed up
11. press mod+p to imput password
12. filename from window will be wired
13. kitty do not support chinese input method, rustup ,cargo and alacritty
14. ranger default text editor
15. 删除团员
16. pynput need sudo apt install python3-tk python3-dev
17. pyautogui 可以弹窗

import pyautogui

# 显示一个简单的带文字和OK按钮的消息弹窗。用户点击后返回button的文字。
pyautogui.alert(text='', title='', button='OK')


~/.fonts/ 添加字体文件，可以直接安装字体
dunst是系统自带的
/usr/share/xsession/dwm.desktop
lsp
dwm-statusbar有时候不显示，是因为temp里多了一对@,不知道为什么
windows的zip文件在ubuntu解压乱码k
