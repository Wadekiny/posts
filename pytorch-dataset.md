---
title: pytorch-dataset
date: 2021-05-14 13:35:51
mathjax: true
tags: [deeplearning, pytorch]
categories:  deeplearning
description: pytorch中和数据集有关的东西

---

# ETL

1. Extract, 提取数据集

2. Transform, 转换为张量

3. Load, 数据放在易于访问的对象中

# torchvision

提供对流行的数据集、模型架构和计算机视觉的图像转换的访问的包

# torchvision.utils

## torchvision.utils.make_gird()

把很多图像的张量拼在一起

```
# 参数：
make_grid(
    tensor: Union[torch.Tensor, List[torch.Tensor]],
    nrow: int = 8,
    padding: int = 2,
    normalize: bool = False,
    value_range: Optional[Tuple[int, int]] = None,
    scale_each: bool = False,
    pad_value: int = 0,
    **kwargs
) -> torch.Tensor:
```

源码： https://pytorch.org/vision/stable/_modules/torchvision/utils.html#make_grid

如果传入图像是单通道灰度图，会转化为三通道的，源码部分：

```
    if tensor.dim() == 4 and tensor.size(1) == 1:  # single-channel images
        tensor = torch.cat((tensor, tensor, tensor), 1)
```

# torchvision.transforms

图像处理的通用转换接口

# 类：Dataset, DataLoader

| class                       | description      |
| --------------------------- | ---------------- |
| torch.utils.data.Dataset    | 一个表示数据集的抽象类      |
| torch.utils.data.DataLoader | 封装数据集，提供对底层数据的访问 |

两个类都是可迭代的，但 DataLoader 可以提供封装 batch 的功能

```python
import numpy as np
import torch
from torch.utils import data
from d2l import torch as d2l

# 生成数据集
true_w = torch.tensor([2, -3.4])
true_b = 4.2
features, labels = d2l.synthetic_data(true_w, true_b, 1000)

# test dataset
dataset =   data.TensorDataset(features,labels)
dataloader = data.DataLoader(dataset, 10)

it_dataset = iter(dataset)
it_dataloader = iter(dataloader) # 10 items in a batch
print("dataset")
print('type', type(next(it_dataset)))
print(next(it_dataset))
print("-"*20)
print("dataloader")
print('type', type(next(it_dataloader)))
print('len', len(next(it_dataloader)))
print(next(it_dataloader))
```

输出：

```text
dataset
type <class 'tuple'>
(tensor([ 0.9377, -1.0325]), tensor([5.2714]))
----------
dataloader
type <class 'list'>
len 2
[tensor([[ 1.1866, -0.5799],
        [-0.5341,  0.9155],
        [ 0.5173,  1.5141],
        [ 0.9799, -0.9593],
        [ 0.8820, -0.2240],
        [-0.6207, -0.0412],
        [ 0.3258, -1.1653],
        [-0.3668, -1.0674],
        [ 0.5764,  0.4123],
        [ 0.2643,  0.4447]]), tensor([[ 4.7781],
        [ 2.4811],
        [ 7.3403],
        [-1.0926],
        [ 5.4263],
        [-0.6430],
        [-1.1687],
        [10.5257],
        [ 3.2337],
        [ 4.1173]])]
```
