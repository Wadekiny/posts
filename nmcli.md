---
title: nmcli 网络连接
mathjax: true
tags: [ubuntu, network-manager, wifi]
date: 2022-06-26 19:43:43
categories: ubuntu 
description: 使用 nmcli 命令进行网络连接
---

# 查看网卡信息
```cmd
// 查看所有网卡的信息
nmcli device
```

# 连接一个新 WiFi
```cmd

// 显示可以搜索到的WiFi
nmcli device wifi list 

// 连接wifi
nmcli device connect $ssid password $password
```

# 连接和断开WiFi
```cmd
// 显示网络连接信息
nmcli c  
// 连接
nmcli c up $ssid
// 断开
nmcli c down $ssid
```
