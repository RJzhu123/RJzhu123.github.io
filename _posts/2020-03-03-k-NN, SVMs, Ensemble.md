---
layout:     post                    # 使用的布局（不需要改）
title:      k-NN, SVMs, Ensemble              # 标题 
subtitle:   ist707-week7 #副标题
date:       2020-03-03              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - machine learning
---

<font size="4"></font><br />

## k-NN, SVMs, Ensemble

### K-Nearest Neighbor (k-NN)
Instance-based Learning，训练时没有分类过程，直到新数据给上，才会有分类/预测过程
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcifjyjjvfj31800t47da.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcifkjuyrlj317q0sudmq.jpg)

**k小对噪声敏感，k大降低准确度**
![](https://tva1.sinaimg.cn/large/00831rSTgy1gciflln7ltj319a0qg7ab.jpg)

#### The shape of decision boundary matters

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcifo7checj31b60t8gun.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcifonfqgnj318e0tc18j.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcifwqnpqwj31040tqjzl.jpg)
没有特别的预先设定的形状，boundary取决于数据本身
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcify3w2wrj31880q20zt.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcig0f0l81j31660fiq7c.jpg)
对噪声和无关变量敏感，**预处理需要remove那些无关变量**

### Support Vector Machines (SVM)
> an algorithm that can solve both linearly separable and inseparable problems

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcig4qtvxgj311u0nkwob.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcig6ki5nuj31260r6jxj.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcig7a1pxuj310e05iwg8.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcig7vc5tkj31460rgwml.jpg)

**support vectors的数量决定了svm模型的复杂度**

![](https://tva1.sinaimg.cn/large/00831rSTgy1gciga1cfy4j31420sewok.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcigb08w6gj30z00a6di7.jpg)

#### Soft Margin SVM
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcigv0nxsfj311q0q4qas.jpg)
参数C代表的是在线性不可分的情况下，对分类错误的惩罚程度
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcigvs8f6aj311u0oq7aj.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcigwmr4zyj31400petdd.jpg)


#### Kernel
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcigxdlt3nj311y0lsdkj.jpg)

#### SVM特点
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcih79lt4sj31040h4td4.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcih7vqrlij30zo0c6dio.jpg)

### Ensemble Methods 集成学习
多个弱监督模型以期得到一个更好更全面的强监督模型，集成学习潜在的思想是即便某一个弱分类器得到了错误的预测，其他的弱分类器也可以将错误纠正回来

- **数据集大**：划分成多个小数据集，学习多个模型进行组合
- **数据集小**：利用Bootstrap方法进行抽样，得到多个数据集，分别训练多个模型再进行组合

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcihsvupe5j30zo0r47d1.jpg)
#### 原理
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcihvi5oozj313o0riwlj.jpg)

#### Bagging
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcihxl36zej31240pydoo.jpg)

#### Boosting
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcihydmkooj312k0nuwku.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcii18driyj314c0o6qbo.jpg)

#### Random Forest
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcii1l7gm9j313o0r0qhh.jpg)