---
title: EfficientDet
categories: Paper
tags:
  - CVPR
  - detection
  - fusion
  - neck
abbrlink: a510d887
date: 2020-8-27 15:12:47
---
<p></p>
<!-- more -->

### 贡献

- 提出高效的特征融合模块BiFPN
  - 去除了只有一个输入的节点
  - 添加额外的连接
  - 特征求和部分添加可学习的权重参数
  - BiFPN多次叠加构成Neck
  ![EfficientDet](EfficientDet.png)
- 用EfficientNet的思路探索了合适的Neck、Head和输入分辨率配置

### 相关

- [EfficientNet](http://blinging.xyz/posts/a8875d51.html)

### BibTeX
```
@INPROCEEDINGS{efficientdet,
  author={M. {Tan} and R. {Pang} and Q. V. {Le}},
  booktitle={Conference on Computer Vision and Pattern Recognition}, 
  title={EfficientDet: Scalable and Efficient Object Detection}, 
  year={2020},
  pages={10778-10787},
  pdf={https://openaccess.thecvf.com/content_CVPR_2020/papers/Tan_EfficientDet_Scalable_and_Efficient_Object_Detection_CVPR_2020_paper.pdf}
}
```

---

