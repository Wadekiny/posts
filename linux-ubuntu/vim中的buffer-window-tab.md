---
title: 'vim:buffer window tab'
mathjax: true
date: 2021-01-01 20:53:33
tags: [vim,ubuntu]
categories: ubuntu 
description: buffer, window, tab是什么
---

## buffer  window  tab 分别是什么

**参考vim的help文件**
A buffer is the in-memory text of a file
A window is a viewport on a buffer
A tab page is a collection of windows.


### Window:

A window is a viewport onto a buffer. You can use mutiple windows on one buffer, or several windows on different buffers.

A screen contains one or more windows, separated by status lines and with the
command line at the bottom.

for example:
```
              screen
 +-------------------------------+
 | window 1      | window 2      |
 |               |               |
 |               |               |
 |= status line =|= status line =|
 | window 3                      |
 |                               |
 |                               |
 |==== status line ==============|
 |command line                   |
 +-------------------------------+
```

### Buffer
A buffer is a file loaded into memory for editing. The original file remains unchanged until you write the buffer to the file.

A buffer can be in one of three states:

1. active: the buffer is displayed in a window. If there is a file for this buffer, it has been read into the buffer. The buffer may have been modified since then and thus be different from the file.
2. hidden: the buffer is not displayed. If ther is a file for this buffer, it has been read into the buffer. Otherwise it is the same as an active buffer, you just cannot see it.
3. inactive: the buffer is not displayed and does not contain anything. Options for the buffer are remembered if the file was once loaded. It can contain marks from the shada file. But the buffer doesn't contain text.

In brief:

| state    | displayed in window | loaded | ":buffers" show |
|----------|---------------------|--------|-----------------|
| active   | yes                 | yes    | 'a'             |
| hidden   | no                  | yes    | 'h'             |
| inactive | no                  | no     | ' '             |

### Tab
A tab page holds one or more windows.  You can easily switch between tab pages, so that you have several collections of windows to work on different things.



### 总结

- 操作文件实际上是操作各个buffer（当新打开一个buffer的时候它不对应任何文件），buffer客观存在（活动、非活动、隐藏），想要看到buffer的内容需要使用window
- window实际上是buffer的视窗，想要看到buffer需要通过window，一个window对应一个buffer；也可以同时用多个window看一个buffer（比如需要对比一个文件的两个不同位置），对buffer的修改同时有效
- 一个tab可以整合多个window，多个window构成一个tab

---

## vim 中 buffer  window  tab 的操作

### buffer

#### 缓冲区列表

1. `:ls`
2. `:buffers`

#### 切换缓冲区

1. 上一个　`:bp`
2. 下一个　`:bn`
3. 指定　`:b[index]`

#### 删除缓冲区
1. 删除当前　`:bd`
2. 删除指定　`:bd[index]`

### window

#### 切分窗口

1. 水平切分   
    命令：`:sp file`
    快捷键：`<Ctrl-w> + s` 
2. 垂直切分
    命令： `:vsp file`
    快捷键：`<Ctrl-w> + v`

#### 关闭窗口

1. 关闭活动窗口
    命令： `:clo  或者 :q`
    快捷键：`<Ctrl-w> + c`
2. 关闭其他窗口
    命令： `:on`
    快捷键：`<Ctrl-w> + o`

#### 切换窗口

1. 窗口间循环切换 `<Ctrl-w> + w`
2. 切换到左边窗口 `<Ctrl-w> + h`
3. 切换到上边窗口 `<Ctrl-w> + j`
4. 切换到下边窗口 `<Ctrl-w> + k`
5. 切换到右边窗口 `<Ctrl-w> + l`

#### 调整窗口

1. 增加活动窗口宽度      `:vertical res +10  ` 
2. 最大化活动窗口的宽度  `<Ctrl-W> + | 　　  ` 
3. 使所有窗口等宽等高    `<Ctrl-W> + =       ` 
4. 设置活动窗口高度为N行 `[N] + <Ctrl-W> + _ ` 
5. 设置活动窗口宽度为N列 `[N] + <Ctrl-W> + | ` 
6. 增加活动窗口高度      `:res +10           ` 

### tab

1. 在新标签页中打开 {filename}         `:tabe(dit) [filename] `	
2. 关闭当前标签页及其中的所有窗口      `:tabc(lose)	          `  
3. 只保留活动标签页，关闭所有其他标签页`:tabo(nly) [filename] `	
4. 切换到编号为 {N} 的标签页           `:tabn(ext) [N} 	      `  
5. 切换到下一标签页                    `:tabn(ext) 	          `  
6. 切换到上一标签页                    `:tabp(revious) 	      `  


---
---



