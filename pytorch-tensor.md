---
title: pytorch-tensor
date: 2021-05-08 22:56:14
tags: [deeplearning, pytorch]
categories: deeplearning 
description: pytorch中tensor的一些特性
---

# 张量（Tensor）的属性

## 数据类型 dtype

张量的互相操作要同类型
新版pytorch自动转换类型

```
>>> t = torch.Tensor()
>>> t.dtype
torch.float32
```

## 在内存中的布局

```
>>> t.layout
torch.strided
```

## 设备

使用多设备时，张量之间的操作必须存在于同一个设备

```
>>> t.device
device(type='cpu')

>>> device = torch.device('cuda:0')
>>> device
device(type='cuda', index=0)
```

## Rank（阶数）

常量： rank 0
向量： rank 1
矩阵： rank 2
n维张量： rank n

## Shape（形状）

**指明每一层有多少个元素**

```
>>> a = torch.Tensor([1,2,3])
>>> a.shape
torch.Size([3])

>>> a = torch.Tensor([[1,2,3],[4,5,6],[7,8,9]])
>>> a.shape
torch.Size([3, 3])

>>> b = torch.Tensor([[1,2],[4,5],[7,8]])
>>> b.shape
torch.Size([3, 2])
```

a.rank = `len(a.shape)`

图像中的例子：

```
# [B,C,H,W]
# [batch, channel, height, width]

# 三幅图，一个通道，2*2大小
# [3,1,2,2]

>>> d
tensor([[[[1., 1.],
          [1., 1.]]],


        [[[2., 2.],
          [2., 2.]]],


        [[[3., 3.],
          [3., 3.]]]])

#------------------
#          Batch1     
#          | Channel1
#          | | Line1
#          | | | Column1
#          | | | |
#          ↓ ↓ ↓ ↓
# tensor([ [ [ [ 1., 1.],
#              [ 1., 1.] ] ],
#                    ↑ ↑ ↑ ↑
#                    | | | |
#                    | | | Batch1
#                    | | Channel1 
#                    | Line2  
#                    Column2   
#
#         [[[2., 2.],
#           [2., 2.]]],
# 
# 
#         [[[3., 3.],
#           [3., 3.]]]])
```

# 创建张量

## 使用现有的数据创建张量

```
>>> data = np.array([1,2,3,])

>>> data
array([1, 2, 3])

>>> type(data)
<class 'numpy.ndarray'>
```

1. 构造函数，使用默认的数据类型，复制数据
   
   ```
   >>> torch.Tensor(data)
   tensor([1., 2., 3.])
   ```

2. **（推荐）工厂函数，使用相同的数据类型（或人为指定），复制数据**
   
   ```
   >>> torch.tensor(data)
   tensor([1, 2, 3])
   ```

3. 工厂函数，使用相同的数据类型（或人为指定），只接受numpy数组，共享数据
   
   ```
   >>> torch.from_numpy(data)
   tensor([1, 2, 3])
   ```

4. **（推荐）工厂函数，使用相同的数据类型（或人为指定），不只是numpy数组，共享数据**
   
   ```
   >>> torch.as_tensor(data)
   tensor([1, 2, 3])
   ```

## 使用特定数据或随机数创建张量

```
>>> torch.eye(3)
tensor([[1., 0., 0.],
        [0., 1., 0.],
        [0., 0., 1.]])


>>> torch.zeros(2,2)
tensor([[0., 0.],
        [0., 0.]])


>>> torch.ones(2,2)
tensor([[1., 1.],
        [1., 1.]])


>>> torch.rand(2,2)
tensor([[0.2826, 0.3104],
        [0.6186, 0.4671]])
```

# 对张量形状的基本操作

## View

view 和 reshape 的区别？

## Reshape

> 怎么实现的？看源码

通过reshape可以改变形状或阶数

**获得元素个数**

```
>>> t = torch.tensor([[1,1,1,1,],[2,2,2,2,],[3,3,3,3,],],dtype=torch.float32)

>>> torch.tensor(t.shape).prod()
tensor(12)

>>> t.numel()
12
```

**元素个数要一样**

```
>>> t = torch.tensor([[1,1,1,1,],[2,2,2,2,],[3,3,3,3,],],dtype=torch.float32)

>>> t.reshape(6,2)
tensor([[1., 1.],
        [1., 1.],
        [2., 2.],
        [2., 2.],
        [3., 3.],
        [3., 3.]])

>>> t.reshape(4,3)
tensor([[1., 1., 1.],
        [1., 2., 2.],
        [2., 2., 3.],
        [3., 3., 3.]])

>>> t.reshape(1,12)
tensor([[1., 1., 1., 1., 2., 2., 2., 2., 3., 3., 3., 3.]])

# 改变阶数

>>> t.reshape(2,2,3)
tensor([[[1., 1., 1.],
         [1., 2., 2.]],

        [[2., 2., 3.],
         [3., 3., 3.]]])
```

## Squeeze

```
# original

>>> t1
tensor([[1., 1., 1., 1., 2., 2., 2., 2., 3., 3., 3., 3.]])
>>> t1.shape
torch.Size([1, 12])

# squeezed
>>> t1.squeeze()
tensor([1., 1., 1., 1., 2., 2., 2., 2., 3., 3., 3., 3.])
>>> t1.squeeze().shape
torch.Size([12])

# unsqueezed
>>> t2 = t1.squeeze()
>>> t2
tensor([1., 1., 1., 1., 2., 2., 2., 2., 3., 3., 3., 3.])
>>> t2.unsqueeze(dim=0)
tensor([[1., 1., 1., 1., 2., 2., 2., 2., 3., 3., 3., 3.]])
>>> t2.unsqueeze(dim=0).shape
torch.Size([1, 12])
```

## flatten

**pytorch自带的flatten()**

```
>>> d
tensor([[[[1., 1.],
          [1., 1.]]],


        [[[2., 2.],
          [2., 2.]]],


        [[[3., 3.],
          [3., 3.]]]])

>>> d.flatten().shape
torch.Size([12])

>>> d.flatten(start_dim=0).shape
torch.Size([12])

>>> d.flatten(start_dim=1).shape
torch.Size([3, 4])

>>> d.flatten(start_dim=2).shape
torch.Size([3, 1, 4])

>>> d.flatten(start_dim=3).shape
torch.Size([3, 1, 2, 2])
```

**自己构造**

```
# 第一种方法

def flatten(t):
    t = t.reshape(1,-1)
    t = t.squeeze()
    return t

# 第二种方法

def flatten(t):
    t = t.reshape(-1)
    # 或 t = t.reshape(t.numel())
    return t

# 起始轴自定义

def MyFlatten(t, start_dim=0，end_dim = -1):

    if start_dim>=0 and start_dim < len(t.shape) and (end_dim == -1 or (end_dim > start_dim and end_dim < len(t.shape) )):
        sp = t.shape
        spn = []
        inin = 1

        for i in range(start_dim, end_dim+1, 1):
            inin *= sp[i]


        for i in range(0,start_dim,1):
            spn.append(sp[i])
        spn.append(inin)
        for i in range(end_dim+1, len(sp), 1):
            spn.append(sp[i])

        spn = torch.Size(spn)

        t = t.reshape(spn)
    else:
        pass

    return t
```

## 同阶合并 cat()

```
>>> a
tensor([[1., 1., 1.],
        [1., 1., 1.]])
>>> b
tensor([[2., 2., 2.],
        [2., 2., 2.],
        [2., 2., 2.],
        [2., 2., 2.]])

>>> torch.cat((a,b),dim=0)
tensor([[1., 1., 1.],
        [1., 1., 1.],
        [2., 2., 2.],
        [2., 2., 2.],
        [2., 2., 2.],
        [2., 2., 2.]])

>>> torch.cat((a,b),dim=1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
RuntimeError: Sizes of tensors must match except in dimension 1. Got 2 and 4 in dimension 0 (The offending index is 1)
```

## 升阶合并 stack()

```
>>> a
tensor([[1., 1.],
        [1., 1.]])

>>> b
tensor([[2., 2.],
        [2., 2.]])

>>> c
tensor([[3., 3.],
        [3., 3.]])

>>> torch.stack((a,b,c))
tensor([[[1., 1.],
         [1., 1.]],

        [[2., 2.],
         [2., 2.]],

        [[3., 3.],
         [3., 3.]]])
```

# 广播（Broadcasting）

# 一些取出张量的操作

## .item()

只适用于仅拥有一个元素的张量，对维数没有要求，返回张量内部的数据（基本的python数字类型）

## .tolist()

类似.item(), 返回list

## .numpy()

Returns self tensor as a NumPy ndarray

## detach(), detach_(), data
