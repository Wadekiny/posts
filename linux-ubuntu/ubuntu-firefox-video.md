---
title: ubuntu下firefox不能播放视频
mathjax: true
tags: [ubuntu,firefox]
categories: ubuntu 
date: 2021-06-09 15:29:33
description: ubuntu18.04, firefox 浏览器播放视频
---

1. 下载 flash 插件，选择 NPAPI 版本
   https://www.flash.cn/

2. 解压，切换至解压后的目录

3. 复制文件
   
   ```bash
   sudo cp libflashplayer.so /usr/lib/mozilla/plugins
   sudo cp -r usr/* /usr
   ```

4. 安装解码器
   
   ```bash
   sudo apt install ffmpeg
   ```

5. 重启浏览器
