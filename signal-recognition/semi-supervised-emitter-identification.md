---
title: 面向非均衡类别的半监督辐射源识别方法
mathjax: true
tags: [paper, radio-signal, deeplearning]
date: 2022-08-21 20:40:57
categories: paper
description: (雷达学报)semi-supervised-emitter-identification.md
---


问题：辐射源个体识别(SEI)中样本标签不完整和数据类别分布不平衡导致分类准确率下降
> 特定辐射源识别(Specific Emitter Identification, SEI)

随着物联网(Internet of Things, IoT)应用的大规模普及和IoT接入设备数 量的迅速增长，高效、安全、稳定的物联网设备认 证方案是防范恶意攻击、确保用户隐私安全的关键[2]。 由于发射机的物理层缺陷不可避免且难以复制，例 如功率放大器的非线性失真[3–5]，因此相比于采用 协议分析、MAC地址关联或密钥验证的无线设备 认证技术，基于物理层射频指纹(Radio Frequency Fingerprint, RFF)提取的SEI方法可靠性更强

## 现有的辐射源识别技术通常 可划分为瞬态方法[6–8]和稳态方法

### 瞬态方法：
瞬态方法利用 发射机开关瞬间产生的状态畸变用于特征提取，但 这类畸变持续时间通常较短，且性能易受噪声及非 理想的信道条件影响发生恶化。

### 稳态方法：
稳态方法从发射机传输的稳定信号中提取RFF用于 分类，因而应用更加广泛。
> 基于物理层射频指纹(Radio Frequency Fingerprint, RFF)

包括高阶累积量(Higher Order Cumulant, HOC)[9,10]、希尔伯特变换(Hilbert Transform, HT)[11–13]、无意调相特征[14]、变分模态 分解(Variational Mode Decomposition, VMD)[15] 和功率谱密度(Power Spectral Density, PSD)但 上述基于变换域分析的稳态特征提取依赖大量的先 验知识，且特征提取的有效性易受传输数据影响， 导致算法的泛化性降低。
