---
title: ubuntu下打包与压缩
date: 2021-01-01 15:53:14
tags: [ubuntu]
categories: ubuntu 
description: tar, zip 等命令的使用
---

linux系统经常使用tar进行归档打包（tar仅仅只能打包），再用gzip，xzip，bzip2等方式压缩（仅仅只能压缩一个文件）
详情可在终端下：`tar -?`

## tar

用法：tar [options...] [file]...
示例：

```
tar -cf archieve.tar foo bar #从文件 foo 和 bar 创建归档文件
tar -tvf archive.tar         #详细列举归档文件 archive.tar
tar -xf archive.tar          #解开归档文件 archive.tar
```

主要操作模式：

```
  -A, --catenate, --concatenate   追加 tar 文件至归档
  -c, --create               创建一个新归档
  -d, --diff, --compare      找出归档和文件系统的差异
      --delete               从归档(非磁带！)中删除
  -r, --append               追加文件至归档结尾
  -t, --list                 列出归档内容
      --test-label           测试归档卷标并退出
  -u, --update               仅追加比归档中副本更新的文件
  -x, --extract, --get       从归档中解出文件
```

提示性输出：

```
  -v, --verbose              详细地列出处理的文件
      --warning=KEYWORD      警告控制:
```

压缩选项：

```
  -a, --auto-compress              使用归档后缀名来决定压缩程序
  -I, --use-compress-program=PROG
                                   通过 PROG 过滤(必须是能接受 -d
                                   选项的程序)
  -j, --bzip2                      通过 bzip2 过滤归档
  -J, --xz                         通过 xz 过滤归档
      --lzip                       通过 lzip 过滤归档
      --lzma                       通过 xz 过滤归档
      --lzop                       通过 xz 过滤归档
      --no-auto-compress           不使用归档后缀名来决定压缩程序
  -z, --gzip, --gunzip, --ungzip   通过 gzip 过滤归档
  -Z, --compress, --uncompress     通过 compress 过滤归档
```

总结：

- *.tar 用 tar -xvf 解压
- *.gz 用 gzip -d或者gunzip 解压
- *.tar.gz和*.tgz 用 tar -xzf 解压
- *.bz2 用 bzip2 -d或者用bunzip2 解压
- *.tar.bz2用tar -xjf 解压
- *.Z 用 uncompress 解压
- *.tar.Z 用tar -xZf 解压
- *.rar 用 unrar e解压
- *.zip 用 unzip 解压

---

---
