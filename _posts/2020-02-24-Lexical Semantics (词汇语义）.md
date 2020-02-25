---
layout:     post                    # 使用的布局（不需要改）
title:      Lexical Semantics (词汇语义）            # 标题 
subtitle:   nlp664-week6 #副标题
date:       2020-02-24              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - nlp
---
<font size="4"></font><br />
## Lexical Semantics (词汇语义）

### WordNet
WordNet is a database of facts about words. 大型英语**词汇数据库**

Nouns, verbs, adjectives and adverbs are grouped into sets of cognitive synonyms (synsets), each expressing a distinct concept.
名词、动词、形容词和副词被分成一系列**认知同义词(synsets)**，每一个都表示一个不同的概念

#### Relations
synsets之间最常见的编码关系是超从属关系(也称为**hyperonymy**上位词（父）、**hyponymy**下位词或**ISA**关系)

除此之外还有，meronym（has part），holonym（part of）. 比如dog 的meronym （tail）
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7vqw792qj31640dm0v5.jpg)
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gc7vrv8es5j30uu0ju7db.jpg" width="80%"/>
#### Ontology 本体论
哲学上，本体论categorizes everything in the world，研究客观事物存在的本质。
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7xrn48mmj318i0ne78w.jpg)

**接下来介绍一些有名的lexicon**

#### Sentiment Lexicon
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7xuo3b73j31eg0u0tgf.jpg)

#### LIWC
Linguistic Inquiry and Word Count  

[http://liwc.wpengine.com/compare-dictionaries/](http://liwc.wpengine.com/compare-dictionaries/)

**Often used for positive and negative emotion words in opinion mining**
用于判断褒义贬义

#### ANEW
Affective Norms for English Words
Participants gave graded reactions from 1-9 on three dimensions：  
**• Good/bad, psychological valence**    
**• Active/passive, arousal valence**    
**• Strong/weak, dominance valence**    
打分制
[https://csea.phhp.ufl.edu/Media.html](https://csea.phhp.ufl.edu/Media.html)

***

### Word Sense Disambiguation (WSD)
人是怎么区分多义词的？ local context，domain knowledge， frequency data

#### Lesk Algorithm
**Measure overlap between sense definitions of a word and current context**

- Identify the correct sense for one word at a time  
-  Current context is the set of words in the surrounding sentence/paragraph/document.

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7yrh1t7qj31bv0u0teb.jpg)
拿到一个word的所有释义，分别算与上下文的意思overlap，取最高overlap的一个释义

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7yw9ya78j31840u0n38.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7yz1hra4j318d0u0grz.jpg)

用人工标签的数据集作为训练集，得到features用于测试集，再回过头来调试features。

![](https://tva1.sinaimg.cn/large/0082zybpgy1gc7z5xux4sj316e0u0dlc.jpg)

除了用overlap也可以用similarity

