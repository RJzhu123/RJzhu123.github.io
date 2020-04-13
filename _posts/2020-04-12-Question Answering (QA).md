---
layout:     post                    # 使用的布局（不需要改）
title:      Question Answering (QA)           # 标题 
subtitle:   nlp664-week14 #副标题
date:       2020-04-12              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - nlp
---
<font size="4"></font><br />

## Question Answering (QA) 
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsiufmcusj31980u07ax.jpg)

**Two-Step**

- use IR to retrieve relevant documents
- apply NLP to find the answer




### Question Classification
 ![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsiwh8obyj313q0u0dlx.jpg)
 
 ![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsj0n33fgj31bi0qagq9.jpg)
 ![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsj1bef2jj317c0n2422.jpg)
 
### Answer Processing
不同question不同方法

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsj3o3ganj319g0u0dlm.jpg)
不常规的问题特殊解决（手动做model等）
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsj6ks66fj31d80skn2e.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsj84uxb2j31bh0u0458.jpg)

 给answers打分，然后选rank最高的
 
 
### IBM watson
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsjbll485j31900u07wh.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsjcske6vj319m0u0tfd.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsjd2vyylj31b00u0n2x.jpg)

### Questions Requiring Complex Answers
Two-stage QA model.  

- Passage retrieval using expanded query representation

- Selection of answer-providing passages based on generic +
specialized entities & relations 

### Conversational Agents
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsjm5mwgrj31cm0u00yp.jpg)

Rule-based chatbots

Frame-based Dialog Agent
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsjq3wjuxj317h0u0k5c.jpg)
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gdsjsvvxxoj31770u00zg.jpg)