---
title: radio-signal-recognition
mathjax: true
tags: [paper, radio-signal]
date: 2022-07-21 12:52:57
categories: paper
description: 无线电信号的检测识别调研
---


# 神经网络方法

## word
### O'shea 
- 输入：时域 I/Q 采样
- 模型：端到端CNN
- 利用 GnuRadio仿真生成了11 种不同调制方式的信号作为训练和测试数据
- 效果：与传统算法的最佳性能相当
-


### 分层识别
- CNN1：区分模拟调制和数字调制
- CNN2：识别具体的调制类型
- CNN3：识别调制的阶数

### 添加时序特征
CNN+LSTM

### 传统方法+CNN
- 原始信息+传统循环平稳特征参数作为CNN输入
- 原始信息+FFT
- 计算复杂度较高


### RadioImageDet
[频谱瀑布图] → CNN特征提取 → 目标检测层 → [波形类型、时/频坐标等]
- 目标检测层以 YOLOv2 为基础

![radioimagedet](./radio-signal-recognition/radioimagedet.png)


### 多尺度深度卷积神经网络

- 输入：WVDM
- 新的激活函数：SELU

![mutiscale](./radio-signal-recognition/mutiscale.png)



## A Survey of Modulation Classification Using Deep Learning: Signal Representatiuon and Data Preprocessing

![survey](./radio-signal-recognition/survey.png)
摘要-- 调制分类是通信系统监测、管理和控制的关键任务之一，用于解决技术问题，包括频谱感知、自适应传输和干扰规避。最近，基于深度学习（DL）的调制分类因其在特征提取和分类精度方面的优势而引起了极大的关注。在基于DL的调制分类中，一个主要的挑战是对接收到的信号进行预处理，并在将信号送入深度神经网络之前以适当的格式表示。本文对最先进的基于DL的调制分类算法进行了全面的调查，特别是这些算法中使用的信号表示和数据预处理技术。由于接收到的信号可以由特征、图像、序列或它们的组合来表示，现有的基于DL的调制分类算法可以分为四组，本文将对其进行相应的回顾。此外，还总结和讨论了每种信号表示方法的优点和缺点。





## Machine Learning Based Automatic Modulation Recognition for Wireless Communications: A Comprehensive Survey
![survey2](./radio-signal-recognition/survey2.png)
