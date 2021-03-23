---
title: SparseNet
categories: Paper
tags:
  - ECCV
  - light-weight
  - backbone
abbrlink: edc10435
date: 2020-09-12 14:02:04
description: <p></p>
---
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

### 问题

- ResNet型密集聚合（+）：聚合后的特征不可分解，深层特征稀释或破坏浅层特征
- DenseNet型密集聚合（concat）：参数以\\(O(N^2)\\)增加，消耗大量参数和运算来处理同一块特征

### 方案

- 保留短梯度路径（skip connection）的优势，但避免类ResNet、DenseNet的稠密聚合
- \\(y_l=F_l(\bigotimes(y_{l-c^0},y_{l-c^1},y_{l-c^2}...y_{l-c^k}))\\)

![](SparseNet.png)

### 相关：

- [PRN](http://blinging/posts/8a14a4e3.html)
- [CSPNet](http://blinging/posts/b956e9d5.html)


>@InProceedings{sparsenet,
>  author={Zhu, Ligeng and Deng, Ruizhi and Maire, Michael and Deng, Zhiwei and Mori, Greg and Tan, Ping},
>  title={Sparsely Aggregated Convolutional Networks},
>  booktitle={European Conference on Computer Vision},
>  year={2018},
>  pages={192--208},
>  pdf={`https://openaccess.thecvf.com/content_ECCV_2018/papers/Ligeng_Zhu_Sparsely_Aggregated_Convolutional_ECCV_2018_paper.pdf`}}

---
