---
layout:     post                    # 使用的布局（不需要改）
title:      Semantic Representation  (语义表征）          # 标题 
subtitle:   nlp664-week7 #副标题
date:       2020-03-01              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - nlp
---
<font size="4"></font><br />
## Semantic Representation (语义表征）

### 1. First Order Logic (一阶逻辑)

- **Constants常量**
-  **Functions 函数**  
	LocationOf()
-  **Variables 变量**

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfylbqpv1j31be0qcgr5.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfymcv7fij313r0u0agd.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyn026o6j319c0q2gr0.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyo2vqyyj31cs0iyzo9.jpg)

#### 特点
词汇表面意思不一定等于实际意思

不是所有逻辑都那么清晰，现实会更复杂

适用于物体+动作的句子，而非理念想法等虚的

### 2.Frames
Frames are a type of structured representation or schema and are widely used for knowledge organization
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyvfj4jfj31am0fwad1.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyvp6cp5j31a60u04jy.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyw010n5j31180u07ci.jpg)

### 3: Semantic Networks
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyy4rmmyj317j0u0wkf.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyzg2woij31ba0u07af.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcfyzvtz0ij319t0u0tep.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1lvirmoj319h0u0dks.jpg)


### Semantic Roles
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1ucb0loj315w0u0n2w.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1v9zjkfj314x0u0afv.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1v260t9j31360aaabp.jpg)

#### Prop Bank
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1vyjau3j31570u0ter.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1weehxgj313y0u01kx.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1x2lu6qj31ca0ac41s.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1xo4lv2j317o0u0q9e.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1yc1t4cj31e50u0jyz.jpg)

#### Frame net
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1z3m6exj31b80tojw0.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg1zr5f04j316f0u0wjd.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg215f0qyj31480u0agn.jpg)

***

### SRL task (semantic role labeling) 算法
前提：  
1. Part-of-speech (POS) tagging  
2. Parse trees or dependency trees

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg25uehl1j312407ywfn.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg2dp36rmj31970u0jym.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg2fabk8nj31fv0u043p.jpg)

首先找constituent然后分析arg，算概率，选概率最高的arg。然后贴label，选概率最高的label

![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg2j8ohyuj318w0t8n2q.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gcg2jkdrhpj31bw0u07ao.jpg)
