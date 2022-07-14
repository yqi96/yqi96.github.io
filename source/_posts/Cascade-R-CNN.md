---
title: Cascade R-CNN
categories: Paper
tags:
  - CVPR
  - cascade
  - two-stage
  - detection
abbrlink: bd869b1e
date: 2019-11-04 10:13:52
description: <p></p>
---

### 问题

- 用低IoU阈值训练的检测器往往会给出带噪的检测结果，但是一味地提升训练时的IoU阈值也会使检测器性能下降。

### 原因

- 随着IoU阈值提高，训练时的正样本数量急剧下降
- 训练时正样本与gt的IoU较高，推理时候选样本和gt的IoU可能没那么高，两者不匹配

### 方案

- 级联回归，每一级一次上调IoU阈值并调整回归误差的均值方差。

### 相关

- 《Object detection with discriminatively trained part-based models》
- 《Object detection via a multiregion and semantic segmentation-aware CNN model》

>@INPROCEEDINGS{cascade,
>  author={Z. {Cai} and N. {Vasconcelos}},
>  booktitle={Conference on Computer Vision and Pattern Recognition}, 
>  title={Cascade R-CNN: Delving Into High Quality Object Detection}, 
>  year={2018},
>  pages={6154-6162},
>  pdf={`http://openaccess.thecvf.com/content_cvpr_2018/papers/Cai_Cascade_R-CNN_Delving_CVPR_2018_paper.pdf`}}

---

