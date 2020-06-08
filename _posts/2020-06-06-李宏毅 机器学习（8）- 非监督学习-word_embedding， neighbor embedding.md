---
layout:     post                    # 使用的布局（不需要改）
title:      李宏毅 机器学习（8）- 非监督学习-word_embedding， neighbor embedding    # 标题 
subtitle:    深度学习        				#副标题
date:       2020-06-06            # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - 李宏毅网课
---
<font size="4"></font><br />

## 李宏毅 机器学习（8）- 非监督学习-word embedding ，neighbor embedding

# Word Embedding
Machine learns the meaning of words from reading a lot of documents without supervision 

## 1、什么是word embedding？
**把每一个word project 到一个high dimension的空间里**

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1bpweldj314v0u0jxw.jpg)


## 2、word embedding 怎么做
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1dgvzbej317w0u0x5e.jpg)

> 不能用auto-encoder来解: 因为1 of n encoding是independent的

我们应该用**上下文**来做这件事
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1fd6mzsj316f0u0dqy.jpg)

### Count Based
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1h11ihgj31bm0si78y.jpg)

### Prediction Based

Given前一个word，predict 后一个word是什么
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1i7wu34j312z0u047i.jpg)


同时呢，要保证类似词汇的output相同，就需要shared parameters
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi1wscpvaj313p0u07wh.jpg)

#### Training

就是把大量的文本信息输入，来无监督地训练模型

#### CBOW 和 skip-gram
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi210try0j317y0u0jxw.jpg)
cbow：前后词predict中间

skip-gram：中间词predict前后词

> 只有一个hidden layer

## 3、word embedding 应用
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi24hkf3rj31bz0u04ku.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2695i4oj316z0u07ar.jpg)

中文、英文做出来的vector没有任何关系

想做multi-lingual embedding，就需要做两个vector，再做一个model，联系起来
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi27ssf0cj31470u0npd.jpg)

### 影像应用
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2953nlvj315w0u07wh.jpg)
好处是遇到trainning set里没有的东西，也能有一个不错的预测


### document embedding
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi28lh03vj316t0u0jxs.jpg)


bag-of-word: 来训练document的正负

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2a7lkw9j31770u0qo8.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2ax0yggj31bz0u00y4.jpg)

但是光用bag-of-word会失去很多重要信息，有其他先进的方法来做。

第一个unsupervised 其他 supervised
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2dbcg3jj31bm0q6tek.jpg)



# Neighbor Embedding

t-SNE 的NE就是neighbor embedding

其实做的就是**非线性的降维**

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2g0qjgoj31540u0e81.jpg)

Manifold learning 就是展开高纬的空间，然后就可以用欧氏几何距离来判断相似性

## LLE

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2ik7mr5j313h0u0gr1.jpg)

Wij就是线性组合的weight

然后进行降维，降维后，wij不变，也就是说她们之间的关系不变
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2k5yaiyj315q0u0grm.jpg)

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2mdq29ij315e0u0e82.jpg)
> 要选取数值合适的k值，也就是neighbor的数量

## Laplacian Eigenmaps

如果你想要比较两点之间的距离，光用欧氏几何距离是不够的，而要看她们在high density的region之间的distance
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2t9psw6j31c10u01kx.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2tknu9aj313i0u04i1.jpg)

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2woci39j31630u00ym.jpg)


Spectral clustering: clustering on z：就是说先用Laplacian Eigenmaps降维后，再用k-means

而z就是graph laplacian的 eigenvector（对应到比较小的eigenvalue)

## t-SNE 
前面的方法只假设相近的点要接近，没有假设不接近的点要分开
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi2ylc4g7j31680u04q4.jpg)

> 右边的圈圈是旋转图片


![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi30ay14jj317b0u0grp.jpg)

找到一个z让 xi对其他point的分布和zi对其他point的分布的kl divergence 越小越好

实际上还是gradient descent来做

> 计算量非常大，通常用快的降维方法例如pca先来做降到比方说50维度，再用tsne降到2维

由于新data会导致重新跑model，所以tsne一般不用在training testing这种base上，而是用在visualization，高纬降到2维度上展示

### similarity measure
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi388brbcj314q0u011d.jpg)

不同的距离function的好处，就是用t分布，原来距离近的点降维后还是很近，原来距离远的点降维后会更远

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gfi3af6b1nj316c0u0h3d.jpg)
