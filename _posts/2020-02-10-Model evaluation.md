---
layout:     post                    # 使用的布局（不需要改）
title:      Model Evaluation              # 标题 
subtitle:   ist707-week5 #副标题
date:       2020-02-14              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - machine learning
---
<font size="4"></font><br />
## Model Evaluation

### Model Overfitting
> Model fits the training data very well, but generalizes to unseen data poorly.   
> Test error-HIGH  Training error-LOW

Higher model complexity -> lower training error -> higher test error
> 例如决策树中，树的node越多，模型越复杂，容易导致overfitting

#### Reason1: noise
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc28vcql9gj30ro0j0ab5.jpg" width="60%"/>

#### Reason2: insufficient samples
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc28wwpt3ij30jk0f4gmk.jpg" width="60%"/>

红色实心+蓝色叉叉为训练集，红色圈圈为测试集   
训练集的数量太少，导致模型没法准确得出正确的pattern来区别红蓝两个类别，从而产生的overfitting

#### Occam’s Razor 奥卡姆法则
> 如果关于同一个问题有许多种理论，每一种都能作出同样准确的预言，那么应该挑选其中使用假定最少的。

如果两个模型有相同的test error，选择更加**简单**的模型而不是复杂的。换言之，evaluate一个模型需要考虑它的模型复杂度。

### Model evaluation methods

#### Hold-out test
给数据集分组，一组为训练集，一组为测试集，通常是7:3    
优点：**简单快速**。  
缺点：**High variability** in the test result。结果不稳定，随着分组的比例变化而变化

#### Cross Validation (CV)
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc298tmyogj30jm0aiaav.jpg" width="80%"/>

通常取n为5或者10
优点：**low variability，稳定**  
缺点：耗时长，慢

#### 两者选择
一般选**Cross Validation**， 数据集很大可以试试**hold-out set**，数据集很小可以考虑**leave-one-out**(LOOCV)

### Metrics for model performance
#### Confusion matrix 
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc29kodfoqj318e0cg798.jpg)

**TP:** 实际、预测都为真  
**FP:** 实际为假， 预测为真  
**TN:** 实际、预测都为假  
**FN:**实际为真，预测为假  

#### Accuracy
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc2a88uaftj30tk042jrw.jpg" width="60%"/>  
Accuracy是最简单明了的方法，但是有局限性，特别是dataset为skewed的情况，也就是说如果dataset 99%的点都是positive的，那么直接所有都预测positive，也能有99%的准确度。但是在数据点balanced的情况准确度还是很适用的。

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc2agfwogdj319q0h47bv.jpg)
两种错误，一种是预测会买，实际不会，wrong target。二是预测不会买，实际会，missed customers。

不同的需求导致对某一类别的错误更加在意，因此需要不同的评价方式。  比如检测垃圾邮件，你肯定希望正常的邮件不被列为垃圾文件，也就是说希望fn较小，希望较大的recall

#### Precision
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc2aaiezbuj313j0u0doh.jpg" width="80%"/>
> Precision：预测为True的点中，对了多少

#### Recall
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc2aet6rtrj313i0u0thk.jpg" width="80%"/>
> Precision：实际为True的点中，对了多少

#### F-measure
当然，一般precision和recall， one goes up， one goes down。实际上我们需要precision和recall都越高越好，这时候就有F-measure派上用场。

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc2aoamnspj30jo04agm1.jpg" width="70%"/>

***

### Feature Selection
- correlation
- Information Gain Based Feature Selection
- Learner Based Feature  
选一种别的算法分别对不同的features set进行train和test，选结果最好的 features set


### Model Good Enough?
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc2bcnx562j319v0u0wp8.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc2bh0nb3fj316o0u0q95.jpg)

如果data sample不够，可以采取以下方法（不展开）  
- **Semi-supervised learning**
- **Active Learning**
- **Crowdsourcing**

课程上的内容比较基础简单，详见islr


