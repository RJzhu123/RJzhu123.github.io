---
layout:     post                    # 使用的布局（不需要改）
title:      Apache Spark 简介（下）              # 标题 
subtitle:   ist718-week4 #副标题
date:       2020-02-15              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - big data
---
<font size="4"></font><br />
## Apache Spark 2.0简介

和1.6主要区别就是以data frames取代了rdds。
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvdy52t2j30hs08emy6.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxve5pltfj30ln0760te.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvepzzdbj30fk084taa.jpg)

***

### 创建dataframes

#### 1.From Row objects:
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvg7yo7tj30b40380sx.jpg)
#### 2.From RDDs:
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvgfbwuyj308u01rwec.jpg)
#### 3.From files:
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvgouc6yj30ie01fdfs.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvgs8gg5j308y01ajr8.jpg)

### dataframes的几点特点

- 在一个column里的所有data的类型应相同
- dataframe 类型可以有等级化：一个column的类型可以是另外一个dataframe
- **不能通过python直接对dataframes进行操作**， 而需要通过spark命令（类sql）来进行**select，modify，filter，join，group 或者aggregate**
- 操作很多为symbolic的
- 在转换之后, Spark 根据column的类型选择最优化的执行方案

### 代码示例

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbxvobrtezj30m406kmy6.jpg" width="80%"/>

#### 1.1 select
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbxvqnft8rj30mh0brabw.jpg" width="80%"/>
<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbxvsqlwepj30mv0bdgn1.jpg" width="80%"/>
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvtc1zyej30ai051gll.jpg)

#### 1.2 改变column名字
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvujs6tuj309n04q0sp.jpg)

#### 1.3 改变column类型
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvtpn0bcj30ah05p3yj.jpg)

#### 2 结合select 和 modify
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvwlm957j30my08zwga.jpg)

#### 3 结合select 和 modify 并使用 sql utility function（fn）
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvy0pqk2j30m40blabw.jpg)
>需要使用fn.lit(2)传入fn函数需要的参数

#### 4 Filtering
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxvzgzx11j30o409i75h.jpg)

#### 5 Joining
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw0masepj30nc09hdhs.jpg)

下面是具体展示（其实和sql是一样的）：

首先是两个数据集
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw497fr3j30h806swfa.jpg)

**5.1 Inner Join**  
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw640xpaj30d605ldg5.jpg)  

**5.2 Left outer Join**  
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw67bnenj30dh05v74k.jpg)  

**5.3 Right outer Join**  
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw6axkdlj30e505sglw.jpg)  

**5.4 Outer join**  
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw6e30hgj30dx06naaf.jpg)

#### 6 Grouping
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxw9loqmej30ly09rjsv.jpg)

#### 7 Aggregate
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwc70wquj30lc0643zc.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwcbx9xhj30eb09bq3v.jpg)

***

### Spark ML
包含多种算法，基于dataframes操作，数据预处理可以通过pipeline
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwftqh81j30mf08pjsi.jpg)

**Estimator工作流程**
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwh10hysj30m107b3zo.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwhrf7e8j30gd0aaab2.jpg)

**Spark ML需要基于dataframes而不是rdds来生成transformer和estimators**
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwjjwez8j30nw05ut9n.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwkga5q4j30p70ac0v4.jpg)
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwlynqh9j30jg083gm5.jpg)

**Pipelines**
![](https://tva1.sinaimg.cn/large/0082zybpgy1gbxwmsf0iij30ph07e75k.jpg)

**Evaluators**
Evaluators用来从一组模型中选出一个最好的（通过比较prediction给出score）

***

### Spark总结

- Apache Spark 是快速，in-memory 计算系统。 **runs on Hadoop**
- Apache Spark 由**driver program, worker nodes, executors and tasks**组成
- **SparkContext**是driver program的核心object
- RDDs是容错率高的可以被平行操作的元素集合。有多种创建方式：parallelize function / textFile sequenceFile
- RDDs有两大类型的操作：**transformations** 和 **actions**.

- MLlib是Spark机器学习的实现包 ： 包括classification, regression, clustering and recommendation.
	- **Transformers** 处理raw数据
	- **Estimators** need to learn something from the data in order to transform the data
	- **Pipelines** 是Transformers 和 Estimators的打包集合

> 我理解的**spark**和**hadoop**的区别和联系就是：  
 
> **Hadoop**实质上更多是一个**分布式数据基础设施**: 它将巨大的数据集分派到一个由普通计算机组成的集群中的多个节点进行存储，意味着不需要购买和维护昂贵的服务器硬件

> **spark**是对那些分布式存储的**大数据进行处理**的工具，具有强大的数据处理能力，但不具备储存能力，一般结合hadoop系统替代操作较慢的mapreduce，也可以和其他的分布式文件系统进行集成运作。

> **spark** 主要特点就是**lazy execution**和**in-memory**


上下两文仅仅是对于718课上知识的一个小总结，还有很多进一步内容值得学习。










