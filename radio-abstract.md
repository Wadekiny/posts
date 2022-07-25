---
title: radio-abstract
mathjax: true
tags: [paper, radio-signal]
date: 2022-07-24 22:52:57
categories: paper
description: 
---


## Iterative Pyramidal Filtering Method for Improved Signal Recognition in Radio Spectrograms

> IEEE WIRELESS COMMUNICATIONS LETTERS, VOL. 11, NO. 6, JUNE 2022

- 大多数基于无线电频谱图处理的现有技术需要相对较高的信噪比，在低/中等信噪比下表现不佳。
- 本文提出了一种基于新型金字塔卷积核的迭代无线电频谱图滤波方法。
- 该方法提高了无线电频谱图中信号成分的可识别性。










## Exploring Self-supervised Learning for Radio Signal Recognition

> 2021 IEEE 23rd Int Conf on High Performance Computing & Communications; 7th Int Conf on Data Science & Systems; 19th Int Conf on Smart City; 7th Int Conf on Dependability in Sensor, Cloud & Big Data Systems & Application

- 很少有方法使用大量未标记数据进行无线信号识别

- 提出了一个自监督学习框架Self-RadioNet，包括两个步骤：
    - 预训练(用于提取特征)
    - 微调(用于无线电信号识别)。

- 提出了数据增强方法
    ![radio-aug](./radio-abstract/radio-aug.png) 
    - 加入高斯噪声

    ![gaosi](./radio-abstract/gaosi.png)

    - 加入载波频率偏移

    ![cfo](./radio-abstract/cfo.png)












## Modulation Recognition of Radio Signals Based on Edge Computing and Convolutional Neural Network

> Journal of Communications and Information Networks, Vol.6, No.3, Sep. 2021

软件无线电（SDR）是一种使用现代软件控制传统“纯硬件电路”的无线通信技术。它可以为构建多模、多频、多功能的无线通信设备提供有效、安全的解决方案。虽然人们对软件无线电的概念和应用进行了大量研究，但很少讨论已建立系统的运行效率。为了缩短映射延迟并减少云中的高计算负载，开发了基于边缘计算的无线电监测系统，以实现对高性能软件无线电应用的灵活、可扩展和实时监测。为了通过边缘计算（EC）促进深度学习（DL）服务部署的边缘智能，我们开发了一种基于注意机制的卷积神经网络（CNN）边缘智能算法，对边缘信号进行调制识别（MR），使MR更接近天线终端。通过对系统和边缘算法的实验，验证了所开发的多功能无线信号监测系统的有效性。

