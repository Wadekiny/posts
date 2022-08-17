---
title: 3D人脸重建论文综述汇总
mathjax: true
tags: [paper, 3Dface, deeplearning]
date: 2022-07-20 14:25:28
categories: paper
description: 3dfacereconstruction_abstracts.md
---
# 几个方向
1. 精细的面部特征，纹理，牙齿...(可能要添加额外的传感器)
2. 让表情更和谐(GCN)?
3. 侧面角度图片重建
4. 任意角度小序列输入重建

# abstracts

## 2021

### CVPR: Riggable 3D Face Reconstruction via In-Network Optimization 

代码： https://github.com/zqbai-jeremy/INORig


- 提出了一种基于单目图像的可装配三维人脸重建方法。
- 联合估计个性化的 "人脸 rig" 和每幅图图像的参数（包括表情，姿势，照明）
- 设计了一个端到端网络，嵌入了一个可微的网络优化器
- 使用一个decoder: 人脸装备(face rig) -> 紧凑的潜在代码(compact latent code)，学习这个 latent code
- 通过估计个性化的人脸装备，使得本方法比静态重建(static reconstructions)表现要好，并且实现了下游应用，如视频重定向。
> 神魔是静态重建？

### CVPR: 3DCaricShop: A Dataset and A Baseline Method for Single-view 3D Caricature Face Reconstruction
- 从二维漫画重建三维漫画
- 引入3DCaricShop，这是一个大规模的3D漫画数据集
- 提出了一种单视角三维漫画重建的基线方法

为了确保忠实地重建可信的脸部变形，
我们建议将**详细的隐式函数**和**参数化的网格表示**的好端连接起来。

1. 注册一个网格模板到implicit generator的输出上，并将注册结果迭代投射到预先训练好的PCA空间上，以解决伪影和自交的问题。
2. 为了处理非刚性注册过程中的大变形，我们提出了一种新的视图协作图卷积网络（VCCCN），从隐式网格中提取关键点，以实现精确的对齐。 
3. 我们的方法能够在预先定义的网格拓扑结构中生成高保真的三维漫画，并可用于动画制作。我们在3DCaricShop上进行了广泛的实验，以验证数据库的重要性和所提方法的有效性。我们将在发表后发布3DCaricShop。
