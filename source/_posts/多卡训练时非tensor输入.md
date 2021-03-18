---
title: 多卡训练时非tensor输入
categories: 代码块
abbrlink: 5a33d4b6
date: 2021-01-18 22:24:24
tags:
    - Pytorch
---

　　DataParallel类的forward中通过scatter方法把输入分配到各显卡，并行计算后通过gather方法进行整合。scatter只实现了对torch.Tensor的按batch维度切分，tuple、list、dict等类则进行递归，其他类型保持不变。
<!-- more -->
　　list：[Tensor1, Tensor2]作为输入，2卡训练，scatter将Tensor1和Tensor2分别切分成2个：Tensor1_a、Tensor1_b、Tensor2_a、Tensor2_b，并把[Tensor1_a, Tensor2_a]作为GPU1的输入，[Tensor1_b, Tensor2_b]作为GPU2的输入。

　　list：[ndarray1, ndarray2]作为输入，2卡训练时，由于该list内的元素都不是Tensor，因此GPU1和GPU2都接受完整的[ndarray1, ndarray2]作为输入。

　　Pytorch 1.7的scatter的具体实现如下：

```Python
def scatter(inputs, target_gpus, dim=0):
    r"""
    Slices tensors into approximately equal chunks and
    distributes them across given GPUs. Duplicates
    references to objects that are not tensors.
    """
    def scatter_map(obj):
        if isinstance(obj, torch.Tensor):
            return Scatter.apply(target_gpus, None, dim, obj)
        if isinstance(obj, tuple) and len(obj) > 0:
            return list(zip(*map(scatter_map, obj)))
        if isinstance(obj, list) and len(obj) > 0:
            return list(map(list, zip(*map(scatter_map, obj))))
        if isinstance(obj, dict) and len(obj) > 0:
            return list(map(type(obj), zip(*map(scatter_map, obj.items()))))
        return [obj for targets in target_gpus]

    # After scatter_map is called, a scatter_map cell will exist. This cell
    # has a reference to the actual function scatter_map, which has references
    # to a closure that has a reference to the scatter_map cell (because the
    # fn is recursive). To avoid this reference cycle, we set the function to
    # None, clearing the cell
    try:
        res = scatter_map(inputs)
    finally:
        scatter_map = None
    return res
```

　　某些情况下可能需要以长度为batchsize的list作为输入。以2卡为例，希望把list的前半分配给GPU1，后半分配给GPU2，这是无法用DataParalle来实现的。采取策略为：list内的元素不用Tensor，可以用np.ndarray或其他类型，这样每张卡上的模型都会接受到完整的list。另外设置一个torch.Tensor类的index变量作为输入，scatter会将index切分成两份。在模型的forward中利用index来获取对应的list切片。

```python
class Model(nn.Module):
    def __init__():
        pass
    
    def forward(x, index):
        x = x[int(index[0]) : int(index[-1]) + 1]
        x = [torch.from_numpy(i).to(index.device) for i in inputs]
        ...

model = nn.DataParalle(Model())
index = torch.tensor(list(range(batch_size))).to(device)
x = [ndarray1, ndarray2, ..., ndarray16]
out = model(x, index)
```



