---
layout:     post                    # 使用的布局（不需要改）
title:      ISLR_Chapter2           # 标题 
subtitle:   ist718-week7 #副标题
date:       2020-03-02              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - statistical learning
---
<font size="4"></font><br />

## ISLR_Chapter3 (线性回归）

### Simple Linear Regression
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfihw6lhzj304s014t8j.jpg)
#### RSS
Residual sum of squares.  
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfihid9nwj304g014t8i.jpg)  
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfikaxux4j309401bt8k.jpg)

#### Least Squares Coefficient Estimate
<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gcfiio57s5j30a10670sz.jpg" width="50%"/>  
矩阵形式  
<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gcgqq72bhnj303v015jr6.jpg" width="30%"/>

#### Evaluation
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfkw54gbaj30og07pt9h.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfkyqb51vj30n606mjsj.jpg)


#### Hypothesis testing 假设检验
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfl39sx4ej30o80ijgob.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfl44ii07j30n10amgn6.jpg)
p value ： 观测值大于|t|的概率

#### RSE 和 r方
残差标准误( residual standard error)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfl8shem0j30m905fwf1.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcflaozdtjj30lo05gdgh.jpg)
> rse 和 r方 是用来量化模型拟合数据的程度

r方更好用，因为在简单线性模型中R^2 = cor^2
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcflchj7lmj30mq053q3j.jpg)

### Multiple Linear Regression
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcgqnkflbvj30fi01tmx2.jpg)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcgqu2150uj30d9032wej.jpg)  
F 统计量需要多大才能拒绝H0，并得出相关性存在的结论呢?  
事实证明，这些问题的答案取决于 n 和 p 的值。如果 n 很大，即使 F 统计量只是略大于 1 ，可能 也仍然提供了拒绝H0的证据。相反，若 n 较小，则需要较大的 F 统计量才能拒绝 H0

当 H0为 真，且误差项 Bi 服从正态分布时， F 统计量服从 F 分布。

#### Forward selection（贪婪）
从null 开始，不断地加，每次选rss最小的variable。 直到某停止条件，例如所有variable 的p值大于阈值。

#### Backward selection （p>n时不能用）
从满variable开始，每次移除pvalue最大的项。直到某停止条件，例如所有variable 的p值大于阈值

#### mixed selection
混合前两种方法


#### categorical变量的处理
创建dummy variable。 总dummy variable数为class数-1。 

例如：某列：ABC  那就变成【是不是A，是不是B】两列

### 线性模型的assumption
1. 可加性

如果不满足，例如x1和x2互相有影响，interaction effect。 就会导致非线性

解决方法：**增加交互项**  + a x1x2
> Hierarchy, 如果x1和x2单独的p值很小，但是交互项p值很大，那么需要把两者的交互项考虑进去

2. 线性性

**多项式回归**拓展模型解决
> 注意过拟合

### 潜在的问题

#### 1. 非线性的响应-预测 关系
残差图( residual plot) 可以用来识别非线性。 即 ei 和 xi的散点图 （简单线性回归模型）

若是图中有明显趋势，说明非线性

**解决方法：lox， 根号， 平方 和其他先进的方法**
#### 2. 误差项自相关 （correlation of error term)
理解：如果重复数据一遍，那么置信区间则会变成根号2倍，影响结果。 

例子：time series时间序列，相邻时间点获得的观测误差有正相关关系  
判断：绘制 时间函数的残差，若有规律，则说明有正相关
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcgrun3ygrj30nq0iz7a5.jpg)
上图没有，中图有一点，下图很明显的跟踪现象

时间引起的可以解决，若以外的数据出现误差自相关，则需要良好的实验设计

#### 3.误差项方差非恒定 (non-constant variance of error term)
可能随着响应值的增加而增加残差图呈漏斗形，可以通过log或者根号做变换，降低异方差性
![](https://tva1.sinaimg.cn/large/00831rSTgy1gch652o1afj30i809k426.jpg)
或者加权最小二乘法拟合模型

#### 4. outlier
y的离群点，**学生化残差 studentized residual**， e除以估计标准误。

**值>3**可能为离群点。 离群点可以直接删掉，但也要注意可能是模型缺陷，缺少预测变量
![](https://tva1.sinaimg.cn/large/00831rSTgy1gch6hdl6jzj30v10ej77e.jpg)
#### 5. high-leverage point
离群点是指对于给定的预测值 Xi 来说，响应值 Yi 异常的点。相反，高杠杆 (leverage) 表示观测点 Xi是异常的。 
![](https://tva1.sinaimg.cn/large/00831rSTgy1gch6juedr9j30ux09u768.jpg)
通过杠杆统计量判断   
<img src="https://tva1.sinaimg.cn/large/00831rSTgy1gch6jxzgo6j30c703mq2y.jpg" width="50%"/>  
#### 6.共线性 collinearity
共线性( collinearity) 是指两个或更多的预测变量高度相关。
![](https://tva1.sinaimg.cn/large/00831rSTgy1gch6mhqvhhj30i608640h.jpg)
共线性降低了回归系数估计的准确性，它会导致beta的标准误变大

判断方法：**看相关系数矩阵**

多重共线性：看方差膨胀因子VIF
![](https://tva1.sinaimg.cn/large/00831rSTgy1gch6pqvamej30n005kjrw.jpg)
我们对每个因子，用其他Ｎ个因子进行回归解释。

VIF 值超过 5 或 10 就表示有共线性问题

解决办法：**1.删去一个。2.把共线变量组合成单一的预测变量**