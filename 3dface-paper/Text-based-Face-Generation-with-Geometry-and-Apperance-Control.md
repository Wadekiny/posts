---
title: 'Text2Face: Text-based Face Generation with Geometry and Apperance Control'
mathjax: true
tags: [paper, text2face]
date: 2022-07-01 12:55:19
categories: paper
description: (s)通过文本生成人脸：Text-Based-Face-Generation-with-Geometry-and-Apperance-Control.md
---

# 相关工作

StyleGAN
geometry features and apperance features
semantic masks

本文:对面部的几何形状(geometry)和外观(apperance)之间的关系进行建模，更容易控制几何和外观特征

# Pipeline

1. 文本处理模块，把输入的句子对应为一组关键词，这些关键词用于从属性库中有条件地抽取特征，用于面部生成
2. 特征提取模块，将每个面部组件的几何形状和外观区分开，用于构建属性库。
3. 图推荐模块，包含两个子模块，分别从几何形状和外观的角度学习面部组件之间的一致性，因此可以对属性库中的部件进行优化，对未指定的面部部位提出建议。
4. 全局生成模块，将生成的部件进行融合。

## Text Parsing Module

## Feature Extraction Module

This module serves for local geometry and appearance disentanglement.

**Input:** real images of facial components $I^r_{part}$ belonging to a whole image $I$

**Output:** 
- geometry features: $f^{geo}_{part}$
- apperance features: $f^{app}_{part}$



## Graph Recommendation Module 

### Geometry Graph 
recommending compatible geometry features for unspecified parts 

### Apperance Graph 
unifying the appearance of generated face image from part-level
