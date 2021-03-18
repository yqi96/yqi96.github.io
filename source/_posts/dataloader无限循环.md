---
title: DataLoader无限循环
categories: 代码块
tags:
  - Pytorch
abbrlink: 52f897dd
date: 2021-01-18 21:51:03
---

```Python
def inf_gen(dataloader):
    while True:
        for item in dataloader:
            yield item
```