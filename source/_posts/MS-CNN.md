---
title: MS-CNN
categories: Paper
tags:
  - ECCV
  - detection
abbrlink: a2ad476c
date: 2019-11-09 12:03:02
---
<p></p>
<!-- more -->

| 问题                       | 方案                                             |
| :--------------------------: |:------------------------------------------------: |
| 感受野和目标尺度不匹配问题 | 多尺度生成proposal，每个特征谱预测特定尺度的目标 |
| 对浅层的BP容易带来训练不稳定 | 在conv4_3后接一个buffer conv层 |
|                           | 与gt的IoU小于0.2的proposal定为负样本             |
| 深层特征对小目标不敏感 | conv4_3的输出上采样2x后作为RoI Pooling的输入     |
| 上下文有利于分割和检测 | RoI的特征和其上下文同时做RoI Pooling并concat |

![Probosal sub-network](RPN.png)

![Object detection sub-network](DET.png)

### BibTeX
```
@InProceedings{mscnn,
  author={Cai, Zhaowei and Fan, Quanfu and Feris, Rogerio S. and Vasconcelos, Nuno},
  title={A Unified Multi-scale Deep Convolutional Neural Network for Fast Object Detection},
  booktitle={European Conference on Computer Vision},
  year={2016},
  pages={354--370},
  pdf={https://arxiv.org/pdf/1607.07155.pdf}
}
```

---


