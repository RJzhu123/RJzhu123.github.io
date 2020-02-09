---
layout:     post                    # 使用的布局（不需要改）
title:      707_2_Association Rules(关联规则)入门          # 标题 
subtitle:   ist707 #副标题
date:       2020-02-09              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - data mining
    
## Association Rules(关联规则)入门

> Frequent Pattern Analysis

**Association rule mining**: Given a set of transactions, find **rules** that will predict the occurrence of an item based on the **occurrences** of other items in the transaction
 ![](https://tva1.sinaimg.cn/large/0082zybpgy1gbqiy2bcd1j30mh08fgn6.jpg)
> 根据不同物件出现的频率找规则

**Application**:

- 产品组合推荐（网购网站，亚马逊等）
- 菜单设计
- 网页设计（点击流分析）
- dna序列分析

**特点**:

- Actionable, 发现的规律可以及时应用
- Trivial, 有时候没什么用
- Inexplicable, 有时候难以解释规则的原因

***

### 基本概念

**itemset**: a collection of one or more items. k-itemset contains k items
          
**3-itemset: {A,B,C}:0, {B, E, F}:2**
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbqj6iowwbj30in0clgmx.jpg)

**Association Rule**

Association rules are generated based on frequent itemsets. We can split a frequent itemsets into two subsets, put one on the LHS, the other on the RHS.
> e.g. { E, F } -> { B } 表示当EF出现的时候，B大概率出现的规则

### Metrics to evaluate the rule’s strength

**Support  P(X, Y)**

- Fraction of transactions that contain both X and Y
- Support({E, F} -> {B}) = support_count({B,E,F}) / N = 2/5

> how many transactions contain them

**Confidence P(Y|X)=P(X, Y)/P(X)**

- How frequently items in Y appear in transactions that contain X
- confidence({E,F} -> {B}) = support({B,E,F}} / support({E,F})

> conditional probability when people bought x, how likely it they also bought Y

***

###Apriori algorithm
Given a set of transactions T, the goal of association rule mining is to find all rules where:

- **support ≥ *minsup* threshold**
- **confidence ≥ *minconf* threshold**

**算法**：

1. Brute-force: 找出所有项，筛出满足条件的项

2. Frequent Itemset Generation：如果一个项集是频繁的，那它所有的子项集也都是频繁的
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbqjld6xo2j30n40eywhq.jpg)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gbqjo1knapj30lq0d6tb0.jpg)

**衡量相关性Lift**
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbqjp2fuomj30jx07q3z3.jpg)

***
那么我们需要怎样大小的support，confidence和lift值呢？
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbqjqm4dy6j30kb0bm3zy.jpg)

### AR小结
作为data mining的一种相当有用的算法，关联规则可以找到一些非常具有insights的规则供我们使用。而Apriori为其中一种算法，可以在r语言中简单使用。在高confidence和lift的rules中选择我们感兴趣的关联规则。
