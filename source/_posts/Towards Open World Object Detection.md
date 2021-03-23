---
title: Towards Open World Object Detection
categories: Paper
tags:
  - CVPR
  - detection
abbrlink: 49a43533
date: 2021-03-11 19:26:54
description: <p></p>
---
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

### 任务
1. open set learning——能识别unknown类的目标
2. incremental learning——能通过后续标注在不忘记旧类的前提下学到新类


### 方法
![Fig. 1 整体框架](framework.png)
#### Contrastive Clustering
为了学到合适的特征空间（同类聚集，异类远离），添加contrastive loss：

$$
\begin{equation}
\mathcal{L}_{cont}(f_c)=\sum_{i=0}^C l(f_c, p_i), where \\

l(f_c, p_i)=\begin{cases}
\mathcal{D}(f_c, p_i), & i=c\\
\max\{0, \Delta-\mathcal{D}(f_c, p_i)\}, & otherwise
\end{cases}

\end{equation}
$$

其中\\(p_i\\)为各类的特征均值（包括unknown），随训练更新，\\(f_c\\)为\\(c\\)类的特征，\\(\mathcal{D}\\)为欧氏距离，\\(\Delta\\)为常数。

#### Auto-labelling Unknowns with RPN
利用RPN所产生的false positive作为unknown类的特征用于上文\\(p_i\\)的更新以及\\(\mathcal{L}_{cont}\\)的计算。false positive根据置信度降序排序，并取top-1。

#### Energy Based Unknown Identifier
用于推理阶段的unknown类决策。定义了一个能量函数：
$$
\begin{equation}
E(f;g)=-T\log\sum_{i=1}^C\exp(\frac{g_i(f)}{T})
\end{equation}
$$
其中\\(g_i(f)\\)是第\\(i\\)类的logit，\\(T\\)是温度常数。

统计了known类和unknown类的\\(E(f|g)\\)取值分布，用韦伯分布来拟合，分别为\\(\xi_{kn}(f)\\)和\\(\xi_{unk}(f)\\)。用\\(\xi_{kn}(f)<\xi_{unk}(f)\\)作为unknown类的判别条件。

能量函数的使用基于Contrastive Clustering已经令unknown类的特征远离known类的特征，这样用unknown类的特征计算的known类的logits相比known类的特征计算的known类的logits整体分布上有差异，呈现Fig. 2状。对两个分布函数的拟合完全没必要，只需要B点的横坐标即可。且实际只要A、B两点的横坐标接近，用什么分布拟合都无所谓。

![Fig. 2 known和unknown的能量分布](dist.png)

#### Alleviating Forgetting
看起来就是incremental learning常规的一套。

### 结论
开放世界目标检测任务的提出以及本文的方法意义不大。从实验设计上看，task2到task4不是few-shot learning，并不适用于online learning。而且全文除了用RPN来生成unknown的伪标签，都跟目标检测没什么关系。

反而是所谓的by-product，显式的open set learning有利于incremental learning，比较有意思。


>@inproceedings{ore,
>  title={Towards Open World Object Detection},
>  author={K J Joseph and Salman Khan and Fahad Shahbaz Khan and Vineeth N Balasubramanian},
>  booktitle={Conference on Computer Vision and Pattern Recognition},
>  year={2021},
>  pdf={`https://arxiv.org/pdf/2103.02603.pdf`}}

---


