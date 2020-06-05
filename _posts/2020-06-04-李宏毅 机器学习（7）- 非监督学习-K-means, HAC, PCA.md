---
layout:     post                    # 使用的布局（不需要改）
title:      李宏毅 机器学习（7）- 非监督学习-K-means, HAC, PCA     # 标题 
subtitle:    深度学习        				#副标题
date:       2020-06-04             # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - 李宏毅网课
---
<font size="4"></font><br />

李宏毅 机器学习（7）- 非监督学习-K-means, HAC, PCA

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh2ewsd01j31cr0u07wh.jpg)
## Clustering

### k-means
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh2hht7hxj319w0ik4hg.jpg)

> 复习，随机取中心，计算每个sample和哪个center最接近，然后同个cluster取平均，平均的值作为新的center，迭代迭代得到最终clusters


### HAC: Hierarchical Agglomerative Clustering

根据data 相似度建立tree，然后切一刀

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh2mbsrtgj315q0p67j7.jpg)

但是仅仅是把example归到某一个cluster，有点以偏概全了，如果用分布来表示就更加科学
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh2nh5eezj317d0u07wh.jpg)

而如果原先的sample是很高纬的数据，这个分布则可以看成 dimension reduction

## PCA
> 718 没怎么做这部分的笔记 这边补上


PCA: 降纬，但是让variance最大

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh6heulumj314y0u07uy.jpg)

### 解法

lagrange multiplier
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh6olopu4j314d0u0njd.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh6rj5tymj313p0u07wh.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh6ttyq02j314n0u04qp.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh6x9tbqaj316i0u04of.jpg)

### 另外一个角度看pca
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh71b8orvj316h0u04qp.jpg)
手写数字辨识：可以看成一堆feature的linear combination

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh77x6nn7j314v0u01is.jpg)
最小化reconstruction error的过程就是解pca的过程

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh79zj6laj31630u0kg6.jpg)
根据svd分解就可以得到pca的解，就是k个最大的covariance matrix的eigenvector

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh7i8fmdtj316m0u0b29.jpg)
pca的过程也可以看成是一个neural network


### pca的weakness
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh7lbcskbj316u0u0b29.jpg)

### 怎么选pca的数量

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh7nmr93xj319w0bs7f3.jpg)

做图看elbow point，最后几个pc往往不能提供过多的信息

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh7tbmk5jj31840u04qp.jpg)


### NMF(让组分只能正向叠加）
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfh7vthoe5j31720t61kx.jpg)

## Matrix Factorization

> 常用于推荐系统， 就是找出背后的latent vector

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi12w82xwj313j0u0kjl.jpg)

- **无missing  value： svd**
- **有missing value ： gradient descent**

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi115f9mej314h0u0npd.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1286gwej318m0u0b29.jpg)