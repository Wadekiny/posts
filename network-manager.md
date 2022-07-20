---
title: network-manager
mathjax: true
tags: [ubuntu, network-manager]
date: 2022-07-19 20:53:03
categories: ubuntu
description: ubuntu18.04 网络管理方式
---

Linux 有两种网络管理方式

1. /etc/network/interfaces(/etc/init.d/networking)

2. Network-Manager

两种管理方式会产生冲突，第一种适合服务器，第二种适合个人电脑

如果Network-Manager发现interfaces被改动，会显示设备未托管

建立dsl连接(先取消自动连接）

sudo pppoeconf

