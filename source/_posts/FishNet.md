---
title: FishNet
categories: Paper
tags:
  - NeurIPS
  - backbone
  - fusion
  - detection
abbrlink: e04a0e51
date: 2018-12-02 00:00:00
---

### 《[FishNet: A Versatile Backbone for Image, Region, and Pixel Level Prediction](http://papers.nips.cc/paper/7356-fishnet-a-versatile-backbone-for-image-region-and-pixel-level-prediction.pdf)》

<!-- more -->

### 问题

- 目前区域/像素级别的任务都在使用分类预训练网络作为backbone，而没有一个专门设计的backbone
- 目前的工作无法直接地将梯度反传到浅层

### 方案

- 提出了FishNet结构（降采样-上采样-降采样结构）

  ![FishNet](FishNet.jpg)

- 对ResBlock进行修改，取消了identity mapping中的卷积，降采样/增加通道放在外部

  ![ResBlock](resblock.jpg)

### 相关

- 《Stacked Hourglass Networks for Human Pose Estimation》
- 《DFANet: Deep Feature Aggregation for Real-Time Semantic Segmentation》
- 《M2Det: A Single-Shot Object Detector based on Multi-Level Feature Pyramid Network》
- 《CBNet: A Novel Composite Backbone Network Architecture for Object Detection》

---
