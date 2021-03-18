---
title: Libra R-CNN
date: 2019-06-16
categories: Paper
tags:
- CVPR
- fusion
- loss
- sampling
- detection
---
### 《[Libra R-CNN: Towards Balanced Learning for Object Detection](http://openaccess.thecvf.com/content_CVPR_2019/papers/Pang_Libra_R-CNN_Towards_Balanced_Learning_for_Object_Detection_CVPR_2019_paper.pdf)》

### 问题

- 1

### 方案

- 1

为什么特征融合后要分别做卷积并加回原feature map?

《[Scale-Aware Trident Networks for Object Detection](http://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Scale-Aware_Trident_Networks_for_Object_Detection_ICCV_2019_paper.pdf)》表示特定的感受野对特定尺度的目标预测效果最佳，直接融合所有尺度的特征不一定有助于所有目标的检测。