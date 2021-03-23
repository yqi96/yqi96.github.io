---
title: ThunderNet
categories: Paper
tags:
  - ICCV
  - two-stage
  - light-weight
  - backbone
  - attention
  - detection
abbrlink: bd9092df
date: 2019-11-05 19:22:11
description: <p></p>
---

### 问题

- 目前没有轻量级二阶段检测模型

### 方案

- backbone
  
  - 着眼运行效率和感受野，以ShuffleNet v2为基础进行修改，将3x3的DW Conv全部改成5x5的DW Conv
- detection head
  - 设计Context Enhancement Module以增大感受野
  
    ![Fig. 1 CEM](CEM.jpg)
  
  - 设计Spacial Attention Module改善用于PSRoI align的特征
  
    ![Fig. 2 SAM](SAM.jpg)
  
  - 用5x5DWConv+1x1Conv取代3x3Conv


![Fig. 3 网络结构](ThunderNet.jpg)

>@INPROCEEDINGS{thundernet,
>  author={Z. {Qin} and Z. {Li} and Z. {Zhang} and Y. {Bao} and G. {Yu} and Y. {Peng} and J. {Sun}},
>  booktitle={International Conference on Computer Vision}, 
>  title={ThunderNet: Towards Real-Time Generic Object Detection on Mobile Devices}, 
>  year={2019},
>  pages={6717-6726},
>  pdf={`http://openaccess.thecvf.com/content_ICCV_2019/papers/Qin_ThunderNet_Towards_Real-Time_Generic_Object_Detection_on_Mobile_Devices_ICCV_2019_paper.pdf`}}

---

