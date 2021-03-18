---
title: TridentNet
categories: Paper
tags:
  - ICCV
  - scale
  - detection
abbrlink: 92fd9c72
date: 2019-10-27 00:00:00
---
### 《[Scale-Aware Trident Networks for Object Detection](http://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Scale-Aware_Trident_Networks_for_Object_Detection_ICCV_2019_paper.pdf)》

<!-- more -->

### 贡献

- 通过对backbone网络的部分层设置不同的扩张率，探索了感受野对目标检测效果的影响

  - 感受野需要和目标尺度相匹配

  - 有效感受野小于理论感受野

  - 感受野需要在大目标和小目标之间找到平衡

- 权重共享，扩张率不同的多条分支生成不同感受野的特征以应对不同尺度的目标

  ![](TridentNet.png)

- 类似SNIP，采用scale-aware的训练方法

- 可以使用主分支检测达到近似三分支的精度(扩展尺度范围为0到∞相当于放弃了scale-aware训练策略？)

---

