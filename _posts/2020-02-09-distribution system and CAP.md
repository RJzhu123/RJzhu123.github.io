---
layout:     post                    # 使用的布局（不需要改）
title:      Distribution system and CAP    # 标题 
subtitle:   718-lecture3 #副标题
date:       2020-02-09              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - [big data]
---

<font size="4"></font><br />
## Distributed systems and CAP
>718-lecture3

## Distributed systems
A distributed system is a collection of independent computers that appear to the users as a single coherent system
>两个程序分别运行在两个台主机的进程上，它们相互协作最终完成同一个服务（或者功能），那么理论上这两个程序所组成的系统，也可以称作是“分布式系统”

#### 优势：
更快，更便宜，更可靠，可扩展

#### 劣势：
- Software must be customized
- 网络设置难
- 程序奔溃的原因更复杂了
- 安全设置难

#### scale up 对比  scale out
- scale up 纵向 

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbr1ice5suj30la0cc449.jpg" width="40%"/>

- scale out 横向 

<img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbr1jri293j30qo096gpe.jpg" width="60%"/>

***

#### CAP Theorem / Brewer’s Theorem
> 参考资料 [https://www.ruanyifeng.com/blog/2018/07/cap.html](https://www.ruanyifeng.com/blog/2018/07/cap.html)

![](https://tva1.sinaimg.cn/large/0082zybpgy1gbr1nhk7dmj31na0t2to0.jpg)
<font size=4>1. Partition tolerance</font>
> Network failures are tolerated, the system continues to operate

**分区容错**. 大多数分布式系统都分布在多个子网络。每个子网络就叫做一个区（partition）。  
分区容错的意思是，区间通信可能失败。比如，一台服务器放在中国，另一台服务器放在美国，这就是两个区，它们之间可能无法通信。  
<center><img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbr1vzts0zj30b208t0sl.jpg"width="40%"/></center>

上图中，G1 和 G2 是两台跨区的服务器。G1 向 G2 发送一条消息，G2 可能无法收到。系统设计的时候，必须考虑到这种情况。  

<font size=4>2. Consistency</font>
>All nodes see the same data at the same time

**一致性**。写操作之后的读操作，必须返回该值。举例来说，某条记录是 v0，用户向 G1 发起一个写操作，将其改为 v1。
<center>
    <img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbr2i0g90yj30as08kmx1.jpg"width="40%"/>
</center>
之后读取就应该得到v1。  

问题是，用户有可能向 G2 发起读操作，由于 G2 的值没有发生变化，因此返回的是 v0。G1 和 G2 读操作的结果不一致，这就不满足一致性了。
<center>
    <img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbr2kz165gj309n08h745.jpg"width="40%"/>
</center>

为了让 G2 也能变为 v1，就要在 G1 写操作的时候，让 G1 向 G2 发送消息，要求 G2 也改成 v1。

<font size=4>3. Availability</font>
>Assurances that every request can be processed.  

只要收到用户的请求，服务器就必须给出回应。

用户可以选择向 G1 或 G2 发起读操作。不管是哪台服务器，只要收到请求，就必须告诉用户，到底是 v0 还是 v1，否则就不满足可用性。

<font size=4>为什么cap不能同时满足</font>
>Suppose we lose communication between nodes:
We must ignore any updates the nodes receive, or sacrifice Consistency, or we must deny service until it becomes Available again.  

简单的说，如果G1变了，那么在同步G2的过程中，G2的读和写都需要被锁定。不然就违背了**一致性**，而若是锁定G2那就违背了**可用性**。而分区容错是一定要有的，因为没人可以保证网络永远不出错。

<font size=4>几个数据库例子</font>
<center><img src="https://tva1.sinaimg.cn/large/0082zybpgy1gbr2v3wrc6j313m0u0tnc.jpg"width="70%"/></center>
