---
title: RPNN
categories: Paper
tags:
  - ICCV
  - relationship
  - Visual Cognition
abbrlink: d3623899
date: 2020-10-21 12:03:42
description: <p></p>
---

### 问题

- 目前的HOI方法从人和物体的特征以及他们的相对位置来预测人物交互，但是人实际是通过身体部件和物体进行交互的，身体部件应该得到更多的关注。

### 方案

- 引入了身体部件特征

- 引入了(人-身体部件)注意力和(物体-身体部件)注意力

![](RPNN.png)

### 相关

- 《[Pairwise body-part attention for recognizing human-object interactions](http://openaccess.thecvf.com/content_ECCV_2018/papers/Haoshu_Fang_Pairwise_Body-Part_Attention_ECCV_2018_paper.pdf)》
- 《[Semi-supervised classification with graph convolutional networks](http://in.arxiv.org/pdf/1609.02907.pdf)》
- 《[Convolutional networks on graphs for learning molecular fingerprints](https://papers.nips.cc/paper/5954-convolutional-networks-on-graphs-for-learning-molecular-fingerprints.pdf)》
- 《[Diffusion-convolutional neural networks](https://papers.nips.cc/paper/6212-diffusion-convolutional-neural-networks.pdf)》

>@INPROCEEDINGS{prnn,
>  author={P. {Zhou} and M. {Chi}},
>  booktitle={International Conference on Computer Vision}, 
>  title={Relation Parsing Neural Network for Human-Object Interaction Detection}, 
>  year={2019},
>  pages={843-851},
>  pdf={`http://openaccess.thecvf.com/content_ICCV_2019/papers/Zhou_Relation_Parsing_Neural_Network_for_Human-Object_Interaction_Dete>ction_ICCV_2019_paper.pdf`}}

---