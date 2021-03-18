---
title: VrR-VG
categories: Paper
tags:
  - ICCV
  - relationship
  - dataset
  - Visual Cognition
abbrlink: bdcfc59d
date: 2019-10-27 00:00:00
---

### 《[VrR-VG: Refocusing Visually-Relevant Relationships](http://openaccess.thecvf.com/content_ICCV_2019/papers/Liang_VrR-VG_Refocusing_Visually-Relevant_Relationships_ICCV_2019_paper.pdf)》

<!-- more -->

### 问题

- 现有的关系预测模型会拟合静态偏差（空间位置、固定搭配等可以从非视觉信息获取的结果）而不是学习视觉信息

### 原因

- 神经网络有强大的从非视觉信息预测的能力

- 空间关系(on、in等)完全可以通过bbox坐标来预测

- 某些关系(wear、ride、has等)可以从语言先验或者统计分析来预测

  ![](distribution2.png)

- 现有数据集有很多上述标签

  ![](distribution1.png)

### 贡献

- 新的关系数据集[VrR-VG](http://vrr-vg.com/)

- 关系感知模型

  - 可以通过坐标、类别等信息来预测的关系是视觉无关的

  - Visual Discriminator: VD-Net通过坐标、类别、词汇等非视觉信息来预测关系
  - 用VD-Net无法准确预测的关系标签来训练视觉感知模型并用于VQA等任务

---