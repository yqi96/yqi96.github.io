---
title: DataLoader无限循环
categories: Code
tags:
  - Pytorch
abbrlink: 52f897dd
date: 2021-01-18 21:51:03
description: <p></p>
---

```Python
def inf_gen(dataloader):
    while True:
        for item in dataloader:
            yield item
```

---
