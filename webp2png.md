---
title: webp2png
mathjax: true
tags: [ubuntu, image]
date: 2022-06-28 12:55:54
categories: ubuntu
description: ubuntu下将webp文件转换为png文件
---

1. 安装webp工具
```cmd
sudo apt install webp
```

2. jpg或png转换为webp:
```cmd
cwebp -q [图像质量] [JPEG/PNG文件名] -o [WebP文件名]
```

3. webp转化为png
```cmd
dwebp [WebP文件名] -o [PNG文件名]
```
