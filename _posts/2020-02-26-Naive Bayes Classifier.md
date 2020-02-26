---
layout:     post                    # 使用的布局（不需要改）
title:      Naive Bayes Classifier              # 标题 
subtitle:   ist707-week7 #副标题
date:       2020-02-26              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - machine learning
---
<font size="4"></font><br />
## Naive Bayes Classifier 朴素贝叶斯分类器

### Bayes Theorem 贝叶斯理论
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcac3n5nboj30z80mcadq.jpg)
一道小题：  
女性得乳腺癌概率为8%。  
如果女性有乳腺癌，她x光阳性的概率为90%。  
如果女性没有乳腺癌，她x光阳性的概率为7%。   
**求女性x光阳性，有乳腺癌的概率为？**

答：9%。   
 0.0072 / （0.0072 + 0.06944）
 
#### 多变量的情况
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcadkk41k8j31540mo45z.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcadm2l4vjj31440tutim.jpg)
通过假设变量independent来减少计算量

尽管一般来说variables相互联系，但是朴素贝叶斯的表现依旧很好。

如果实在要特别考虑变量间的关系，使用**Bayesian Belief Network (BBN)** 贝氏网路替代

#### exercise
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcae9wweenj30wu0n8djn.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcae91xulfj31000kiq8i.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcaeaaq9jej311c0l8afx.jpg)

注意，由于数据量不足，这里出现了0，那么怎么处理0的情况呢？ smoothing！

#### Smoothing
用特别特别小的概率代替0，然后把其他变量的概率稍微变小点，保持总和为1

**1. Laplace Smoothing**   

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gcaed13263j30fm086mxr.jpg" width="40%"/>

其中 c 为class 的数量，例如癌症的例子，就是c = 2


**1. Add-one smoothing**   
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcaeetoq2cj31500oaqcy.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcaefglpjpj314k090n0u.jpg)


#### log
因为现实中的概率都是特别小的，我们可以通过log来避免储存过多的0

### 对于连续变量的贝叶斯
![](https://tva1.sinaimg.cn/large/0082zybpgy1gcaej4z6zwj312s0ocqau.jpg)
**离散化** 或者 **估计分布模型后使用概率密度函数来计算**

![](https://tva1.sinaimg.cn/large/0082zybpgy1gcaelcxfefj314k0nktl9.jpg)

### 朴素贝叶斯步骤
#### 得到分类器
1. 从样本得到先验分布𝑃(𝑌=𝐶𝑘)(𝑘=1,2,...𝐾)
2. 得到条件概率分布𝑃(𝑋=𝑥|𝑌=𝐶𝑘)=𝑃(𝑋1=𝑥1,𝑋2=𝑥2,...𝑋𝑛=𝑥𝑛|𝑌=𝐶𝑘)
3. 用贝叶斯公式得到X和Y的联合分布P(X,Y)
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gcaf1obhdhj310q0skwxt.jpg" width="90%"/>


#### 预测

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gcaf05a1h2j30w40du416.jpg" width="70%"/>

**别忘了对0的概率smoothing**

### 朴素贝叶斯总结
原理简单、每一个数据都能对最后的预测做出贡献、能够给出概率化的预测

![](https://tva1.sinaimg.cn/large/0082zybpgy1gcaepr9zbxj311g0godl1.jpg)

需要概率的知识、对于连续化变量需要做出分布的预测，一般正态分布。

变量independent的假设有时不成立，需要利用**Bayesian Belief Network (BBN)** 贝氏网路替代
