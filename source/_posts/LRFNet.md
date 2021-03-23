---
title: LRFNet
categories: Paper
tags:
  - ICCV
  - scratch
  - detection
abbrlink: 127af3
date: 2019-11-08 09:47:32
description: <p></p>
---
### 问题

- 现有多数目标检测网络是从ImageNet预训练的分类网络微调的，但是检测和分类任务对平移的敏感性要求不同，预训练网络和检测任务之间有一定差异，用分类预训练网络不是最优的。但是从头开始训练检测网络需要大量时间。

### 贡献

- 用分类预训练网络做主体，外接一路从头训练的小网络，结合两者特征

![](LRF.png)

>@INPROCEEDINGS{lrfnet,
>  author={T. {Wang} and R. M. {Anwer} and H. {Cholakkal} and F. S. {Khan} and Y. {Pang} and L. {Shao}},
>  booktitle={International Conference on Computer Vision}, 
>  title={Learning Rich Features at High-Speed for Single-Shot Object Detection}, 
>  year={2019},
>  pages={1971-1980},
>  pdf={`http://openaccess.thecvf.com/content_ICCV_2019/papers/Wang_Learning_Rich_Features_at_High-Speed_for_Single-Shot_Object_Detection_ICCV_2019_paper.pdf`}}

---

