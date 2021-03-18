---
title: PRN
categories: Paper
tags:
  - ICCV
  - light-weight
  - backbone
  - gradient
abbrlink: 8a14a4e3
date: 2019-10-27 00:00:00
---

### 《[Enriching Variety of Layer-wise Learning Information by Gradient Combination](https://openaccess.thecvf.com/content_ICCVW_2019/papers/LPCV/Wang_Enriching_Variety_of_Layer-Wise_Learning_Information_by_Gradient_Combination_ICCVW_2019_paper.pdf)》

<!-- more -->

### 问题

- 之前的文献关注如何组合特征和如何使梯度得以传播，但是否可以通过得到更丰富的梯度组合来提高网络性能？

### 方案

- 部分通道求和（下图中的特征谱按对应颜色的箭头进行正向传播）
![PRN-shrink](PRN-shrink.png)
![PRN-expand](PRN-expand.png)
![PRN-bottleneck](PRN-bottleneck.png)

### 优势

- 更丰富的梯度传播路径
![](grad.png)
- 网络结构的灵活性
- 轻量

### 相关

- [SparseNet](http://blinging.xyz/posts/edc10435.html)
- [CSPNet](http://blinging.xyz/posts/b956e9d5.html)

---
