---
title: CSPNet
categories: Paper
tags:
  - CVPR
  - light-weight
  - backbone
abbrlink: b956e9d5
date: 2020-06-16 00:00:00
---
<p></p>
<!-- more -->

### 贡献

  - 相比PRN，不但增加了梯度组合，还减少了运算
  - 灵活性更强

### 方案

  - 按通道将特征谱分成两份，其中一份接各种模块后和另一份融合
    ![](CSP-dense.png)
    ![](CSP-res.png)
    
### 相关
- [SparseNet](http://blinging.xyz/posts/edc10435.html)
- [PRN](http://blinging.xyz/posts/8a14a4e3.html)

>@INPROCEEDINGS{cspnet,
>  author={C. {Wang} and H. {Mark Liao} and Y. {Wu} and P. {Chen} and J. {Hsieh} and I. {Yeh}},
>  booktitle={Conference on Computer Vision and Pattern Recognition Workshops}, 
>  title={CSPNet: A New Backbone that can Enhance Learning Capability of CNN}, 
>  year={2020},
>  pages={1571-1580},
>  pdf={`https://openaccess.thecvf.com/content_CVPRW_2020/papers/w28/Wang_CSPNet_A_New_Backbone_That_Can_Enhance_Learning_Capability_of_CVPRW_2020_paper.pdf`}}

---