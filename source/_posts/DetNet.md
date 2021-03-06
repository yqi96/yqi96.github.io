---
title: DetNet
categories: Paper
tags:
  - ECCV
  - backbone
  - detection
abbrlink: a562ac22
date: 2019-11-10 13:59:02
description: <p></p>
---

### 问题

- 分类网络的设计准则（大幅降采样）不适合检测任务（定位）
- RPN等网络虽然进行了优化，但仍有一些问题
  - backbone的阶段（stage）数和检测的阶段数不同
  - 由于深层特征谱的大步长，大目标定位不准确
  - 小目标在降采样过程中消失

### 方案

- 设计新的backbone
  - stage数和检测相同
  - 深层stage保持较高的分辨率
  - 通过扩张残差块增大感受野

  ![overview](overview.png)
  ![detail](detail.png)

### 缺陷

- 仍需ImageNet预训练

### 代码

- [https://github.com/zengarden/DetNet](https://github.com/zengarden/DetNet)

>@InProceedings{detnet,
>  author={Li, Zeming and Peng, Chao and Yu, Gang and Zhang, Xiangyu and Deng, Yangdong and Sun, Jian},
>  title={DetNet: Design Backbone for Object Detection},
>  booktitle={European Conference on Computer Vision},
>  pages={339--354},
>  year={2018},
>  pdf={`https://eccv2018.org/openaccess/content_ECCV_2018/papers/Zeming_Li_DetNet_Design_Backbone_ECCV_2018_paper.pdf`}}

---

