---
layout:     post                    # 使用的布局（不需要改）
title:      Decision tree入门               # 标题 
subtitle:   ist707-week5 #副标题
date:       2020-02-14              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - machine learning
---
<font size="4"></font><br />
## Decision Tree
> 707-5

![](https://tva1.sinaimg.cn/large/0082zybpgy1gbvcy5ys3mj313c0tyqa1.jpg)

### 算法
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbwlg5x49jj30ln08wjsa.jpg"width="80%"/>

#### 树的分叉方式: 两分叉或者多分叉
#### 1.Categorical Attributes
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwlkd7ce1j30tu0kmq5i.jpg)
#### 2.Continuous Attributes
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwlkaiegrj30v60jqwhc.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwlmcbhp3j30sm0fodiv.jpg)

#### 树选择哪个属性作为node？

#### Entropy (熵）
> 类似理工科中的熵，形容混乱的程度

> measure the impurity of a data set (Noise Level)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwlpapyhuj30nn02kq34.jpg)
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbwlpk2zchj30s0080js7.jpg"width="90%"/>

一半一半的时候熵值为1， 全为某个值的时候熵为0（极限）
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbwlrjybb0j30h80bqjta.jpg"width="70%"/>


#### Information Gain (IG) -信息增益
> A statistical measure that measures how well a given attribute separates the training examples according to their target classification. (Mitchell,1990)

> ig意义就是经过分支后，熵的变化程度

> 树的分支就是选择最高ig的分支方案, 直到pure为止，或者达到某一设定值，或者满足最大分支数

![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwlxwcuxfj30sa0ju78e.jpg)

> 总熵-分支的熵的和即为ig的值


#### Gain Ratio -信息增益率
> Impurity measures tend to favor attributes that have a large number of distinct values

按照信息增益选择，总是会倾向于选择分支多的属性，这样会是的每个子集的信息熵最小。例如给每个数据添加一个第一无二的id值特征，则按照这个id值进行分类是获得信息增益最大的，这样每个子集中的信息熵都为0，但是这样的分类便没有任何意义，没有任何泛化能力，类似过拟合。

因此使用一个值SplitInfo来作为分组过多的惩罚，讲ig除以SplitInfo的值定为Gain Ratio
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwm5yqb1tj309001rt8o.jpg)  
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwm6axa0hj305h01s3yd.jpg)

#### Gini impurity -基尼不纯度
> 这里引用[化学狗码砖的日常的知乎回答](https://zhuanlan.zhihu.com/p/27905967)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gbwm9i1pd8j30jp0b1ab8.jpg)
基尼系数，也就是另外一种作为分离依据的公式，应用在其他树算法中

#### Decision Tree 的解释
看作if else 的嵌套进行理解

#### Decision Tree 的应用范围：非线性关系
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbwmcw6qe6j30vi0fg0vy.jpg"width="70%"/>

#### overfitting -过拟合 

模型越复杂，越容易过拟合，所以应该选择适当的树大小，也是一种bias和variance的trade-off

- **Prepruning -预剪枝**

该方法是在建立决策树的过程中，判断当决策树的node满足一定条件(比如当树的深度达到事先设定的值，或者当该node下的样例个数小于等于某个数)时，不在继续建立子树，所以也叫Early stopping。
> 选择合适的threshold很难

- **Post-pruning -后剪枝**

先建立完整的决策树，然后通过一定的算法，将某个非leaf node设为leaf node(即将该node下的子树丢弃)实现pruning。
> 使用非训练集的数据来决定怎么剪


### 小结

- 树的优点：预测快， 可解释性强， 抗噪声强

- 树的缺点：容易过拟合，不适用于太多class的分类， 计算废资源

> 作业使用weka的J48算法，这里不再描述。