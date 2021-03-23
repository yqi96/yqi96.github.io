---
title: DAFS
categories: Paper
tags:
  - ICCV
  - detection
abbrlink: 102b1f4c
date: 2019-11-12 10:37:45
description: <p></p>
---

### 问题

- RefineDet的ODM预测时规则卷积的感受野和refine过的anchor位置不匹配

### 方案

- 提出Dynamic Anchor Feature Selection(DAFS)，根据refine后的anchor动态地选择特征
- 改进RefineDet的TCB模块，双向聚合特征谱

>@INPROCEEDINGS{dafs,
>  author={S. {Li} and L. {Yang} and J. {Huang} and X. {Hua} and L. {Zhang}},
>  booktitle={International Conference on Computer Vision}, 
>  title={Dynamic Anchor Feature Selection for Single-Shot Object Detection}, 
>  year={2019},
>  pages={6608-6617},
>  pdf={`http://openaccess.thecvf.com/content_ICCV_2019/papers/Li_Dynamic_Anchor_Feature_Selection_for_Single-Shot_Object_Detection_ICCV_2019_paper.pdf`}}
---