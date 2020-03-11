---
layout:     post                    # 使用的布局（不需要改）
title:      Unsupervised Learning           # 标题 
subtitle:   ist718-week9 #副标题
date:       2020-03-10              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - statistical learning
---
<font size="4"></font><br />

## Unsupervised Learning 

数据集只有 x1, x2, x3， 没有y.  
 我们获得unlabeled data 要比 labeled data 更容易

### Principal Components Analysis
> a tool used for data visualization or data pre-processing before supervised techniques are applied

It finds a sequence of linear combinations of the variables that have maximal variance, and are mutually uncorrelated。 降纬度
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpj1f0pxzj30ve0li430.jpg)
通过loading的平方和为1，计算出方差最大的z （先对数据进行标准化）
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpj3zhv7dj30vw0n60vz.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpjg3ucocj30um0acac2.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpjfqe0h2j30um0ecmzg.jpg)
就是将变量投影到特征空间的一个方向上（该方向，数据分布差异化最明显）
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkc4lu8ej310m0r843g.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkpwnhkyj30yq0qo43s.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkq5l1b6j30vs0pk0w9.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkpe4fjfj30zs0kcwic.jpg)
多少数量，看elbow拐点

### Clustering
> a broad class of methods for discovering unknown subgroups in data

- K-means clustering
在707也有介绍
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkv90debj30z20q8wk9.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkvkemocj30y20lgn0m.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkwj5w84j30yc0l2q7c.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpkzcsuhsj30qe0qg0yn.jpg)
- hierarchical clustering

kmeans要求我们制定k的值，而hierarchical clustering不用
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcpl7ryyxej30va0pkwip.jpg)

### conclusion
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcppx3cjq3j30x20mggqb.jpg)