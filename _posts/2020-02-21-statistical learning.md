---
layout:     post                    # 使用的布局（不需要改）
title:      Statistical learning              # 标题 
subtitle:   ist718-week6 #副标题
date:       2020-02-21              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - statistical learning
---
<font size="4"></font><br />

## Statistical learning 
> 终于到了关键的知识点的, 不错不错

#### 什么是machine learning
开篇概念：

> How can a **machine learning algorithm** use experience to **improve future performance**

其中Experience = **Data**，Future = **Data not yet seen**，Performance = **Error function** or **loss function**

#### 什么是Statistical Learning

> Statistical learning refers to a vast set of tools for **understanding data**. These tools can be classified as supervised or unsupervised  ---ISLR


#### Supervised statistical learning 
> Building a statistical model for predicting, or estimating, an output **based on one or more inputs**

有期望得到的分类或者数值。 

Each X (observation) is associated with a Y (target)


- Linear Regression
- Decision Trees
- Deep Learning
- Support Vector Machine

#### Unsupervised statistical learning 
> there are inputs but **no supervising output**; nevertheless we can learn **relationships and structure** from such data

没有预计得到的output，但是可以分析数据之间的关系或者结构

We have X but no Y (target)


- Hierarchical Clustering
- K-Means
- Mixture Models
- Self Organizing Maps
- Autoencoders
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc3zf7fvzjj30tm0h4wh9.jpg)
**聚类、媒体分类文本、降维（pca）**


*** 

主要以supervised为例， 就是想得到一个映射，从f(x)可以得到y.

但是其中有noise不可避免
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc3zkutqmuj30u90am0ty.jpg)

#### Reducible and Irreducible Error
用squared error来推导
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc3zng6gw8j30q907m753.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc401y2drhj30qo0ceac2.jpg)
重点就是noise是正态分布的，所以期望为0，而且平方的期望等于方差。

**红色**框框则为**Reducible Error**，**蓝色**框框则为**Irreducible Error**

- Reducible具体意义就是error that can be reduced by optimizing hyper parameters of f(x)。让我们模拟的f(x)更加接近真实的f(x)。
- Ireducible具体意义就是不可预测的误差，类似于实验总会有误差，给出的dataset总有没考虑到的feature，而且取样会有误差

*** 

### Estimate f
**Inference**: Apply model on unseen data to assess performance.
#### Parametric Methods (参数法）
> Makes an assumption about the shape of f，then use a procedure to fit or train the model and reduce the loss function for the model

对现有的sample进行一个假设，例如线性关系，然后通过调参训练，减少loss function来得到一个较好的模型

#### Nonparametric Methods （非参数法）
> Don’t make assumptions about f，try to get as close as possible to the training data but not too close，**the more data, the better the fit, but the harder to interpret.**

不进行假设，就是尽量拟合数据，数据越多，效果越好，但是难以解释model，interpret。 比如**随机森林**

#### Maximum Likelihood Estimation (MLE 极大似然估计）
> Estimate the probability distribution parameters that are most likely to best represent the data.

如果数据是正态分布，那么就预估它的mean和std来得到一个最接近的分布
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc40mtlzs0j30ni07b0tr.jpg)
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc40panybxj30cp03fweo.jpg" width="60%"/>

极大似然估计就是计算当概率最大的时候的mean和std值，也就是找到了最符合data的分布
> MLE can be applied to any probability distribution

ps：在线性回归中，mle得到和least squares同样的公式

[具体推导见此回答，非常详细](https://stats.stackexchange.com/questions/253345/relationship-between-mle-and-least-squares-in-case-of-linear-regression)

这里就简单给一个最后的公式吧

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc412h0jgkj30cv01oaa0.jpg" width="40%"/>

### 小结
简单开个头，具体islr内容再补充ing...
