---
layout:     post                    # 使用的布局（不需要改）
title:      Sentiment Analysis             # 标题 
subtitle:   nlp664-week9 #副标题
date:       2020-03-10              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - nlp
---
<font size="4"></font><br />
## Sentiment Analysis

### 简介和需要解决的问题
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco0sbq8hnj31ao0tyn12.jpg)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco0vcgezij31900u0gqg.jpg)
语义文本分为主观部分和客观部分

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco0x3pdqqj317l0u0n4w.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco151a4wsj316f0u0n2p.jpg)

可以只判断积极消极，也可以打分，也可以做opinion mining（难度逐渐变大）

> 有些时候可能有讽刺或者暗喻sarcasm or metaphor  
> 或例如a great deal 只是一个短语

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco1nz6uk9j31cz0u0gso.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco1obkz2ej31970u079w.jpg)

### 具体方法
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco1pgoo4qj31dg0u0gr8.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2hu0939j31c40u0ae2.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2is1632j315m0f2gnu.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2k4j8saj318u0s6q6s.jpg)
#### 处理消极值
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2kszz1hj318v0u0gqu.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2o3i14kj319g0sg794.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2obubj0j318b0u0wk9.jpg)

#### Sentiment Lexicons 特殊词汇
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2svzm5nj319k0sa0ya.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2wb30cbj319r0u0qb4.jpg)
[https://mpqa.cs.pitt.edu/lexicons/subj_lexicon/](https://mpqa.cs.pitt.edu/lexicons/subj_lexicon/)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2xjee2fj31aw0u00xz.jpg)
[http://liwc.wpengine.com/](http://liwc.wpengine.com/)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2y48mcoj31a60u0dlj.jpg)
[https://csea.phhp.ufl.edu/Media.html](https://csea.phhp.ufl.edu/Media.html)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2z0jczfj313r0u0n3c.jpg)
[http://www.wjh.harvard.edu/~inquirer/](http://www.wjh.harvard.edu/~inquirer/)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco2zpthwqj315m0mqdja.jpg)
[https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html](https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco30auc23j31ai0rk0xo.jpg)
[http://sentiwordnet.isti.cnr.it/](http://sentiwordnet.isti.cnr.it/)


**很多时候自己建的lexion效果更好**

![](https://tva1.sinaimg.cn/large/00831rSTgy1gco35fmzutj31780eomzv.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gco36224klj318y0m8jv2.jpg)
