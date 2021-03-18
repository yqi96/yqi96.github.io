---
title: InceptionConv
categories: Paper
tags:
  - CVPR
  - detection
  - backbone
abbrlink: 9bf2951e
date: 2021-03-05 22:16:23
---

### 《[Inception Convolution with Efficient Dilation Search](https://arxiv.org/pdf/2012.13587.pdf)》

<!-- more -->


讲的感受野的故事，结构上就是一个不同分支用不同扩张卷积的Inception块，配合网络结构搜索（剪枝）来确定具体参数。

![](IC-Conv.png)