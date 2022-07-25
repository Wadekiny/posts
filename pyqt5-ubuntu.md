---
title: pyqt5-ubuntu安装
mathjax: true
tags: [qt]
categories: qt  
date: 2021-08-16 20:30:56
description: 安装pyqt5
---

```shell
pip3 install pyqt5
```

问题：

```shell
wadekiny-R7P > pip3 install pyqt5 
Collecting pyqt5
  Using cached https://files.pythonhosted.org/packages/8e/a4/d5e4bf99dd50134c88b95e926d7b81aad2473b47fde5e3e4eac2c69a8942/PyQt5-5.15.4.tar.gz
    Complete output from command python setup.py egg_info:
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
      File "/usr/lib/python3.6/tokenize.py", line 452, in open
        buffer = _builtin_open(filename, 'rb')
    FileNotFoundError: [Errno 2] No such file or directory: '/tmp/pip-build-4rha_wmw/pyqt5/setup.py'

    ----------------------------------------
Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-build-4rha_wmw/pyqt5/
```
