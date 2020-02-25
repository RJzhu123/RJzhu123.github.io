---
layout:     post                    # 使用的布局（不需要改）
title:      ISLR_Chapter2           # 标题 
subtitle:   ist718-week6 #副标题
date:       2020-02-24              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - statistical learning
---
<font size="4"></font><br />

## ISLR_Chapter2

### 建模的意义

- 预测prediction：预测Y，f(x)可以看作黑箱
- 推断inference：变量对于Y产生了什么样的影响

### 估计f的方法

- 参数法：假定是线性的，或者其他模型，然后训练模型，例如最小二乘法，得到最佳的参数
- 非参数法： 不需要对函数f的形式事先做明确的假设。追求的是接近数据点的估计，估计函数在去粗和光滑处理后尽可能与更多的数据点接近，拟合好。**缺点：往往需要大量的观测点**

### 准确度和可解释性Trade-off
模型预测的准确度和可解释性不可兼得。

复杂灵活的模型，准确度高，解释性差。
简单固定的模型，准确度低，解释性好。
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc76mo9cekj30qc0hhjsl.jpg)

### Evaluation

#### MSE均方误差
MSE (mean squared error).  

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc76ocgassj309n02v749.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc76tzxepdj30q20eiq52.jpg)

随着train MSE的不断变小（直至过拟合），test MSE则有一个最低点，不会一直变小。

我们的目的就是得到最小的 test MSE。

### bias 和 variance Trade-off
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc76xgyz62j30o302zt8u.jpg)

flexibility 增加， variance 增加

***

evaluation内容在另外一篇中
[evalutaion](https://rjzhu123.github.io/2020/02/14/Model-evaluation/)


