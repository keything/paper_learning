
+ 论文：[Total Order Broadcast and Multicast Algorithms: Taxonomy and Survey](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.110.6701&rep=rep1&type=pdf)
+ 概述：该文章对于Total Order Broadcast 进行全方面的论述，包括全序广播的详细说明，不容错的全序广播算法的分类、容错的全序广播方法。
+ 我的理解：这篇论文让我知晓了全序广播的属性、有哪些实现方法（非容错、容错）、以及 知道共识与全序广播的关系。这篇文章共识与全序广播的关系概括为：
	+ 全序广播可以归纳为共识问题，容错，包括错误检测、消息稳定性检测 都包含在共识这个抽象中。 
	
## 序言

在容错的分布式系统中，全序广播（total order broadcast） 是一个广播：多进程系统中全部正确的进程都能够以相同顺序收到相同内容消息。 
当然全序广播又叫原子广播(atomic broadcast)，因为对于全部参与者而言，最后要么全部成功，那么没有副作用的终止。

## Total Order Broadcast 详细说明


1. Notation
2. 处理失败
3. Total Order Broadcast 基本的详细说明


+ Validity （合法性）：如果一个进程广播了一条消息，那么一定会被接收。
+ Uniform Agreement （协商一致性）：所有节点接收相同的决议
+ Uniform Integrity（诚实性）：所有节点不能反悔，即对一项提议不能有两次决定
+ Uniform Total Order（协商全序）：


满足前三个的是Reliable broadcast，满足全部的才是Total Order Broadcast。


关于活性liveness 和 安全性safety的介绍

+ Validity and Uniform Agreement 是liveness属性。 this means that, at any point in the time, no matter what has happened up to that point, it is still possible for the property to eventuall hold. 
+ Uniform Integrity and Uniform Total Order are safety properties. This means that, if, at some point in time, the property  does not hold, no matter what happends later, the property cannot eventually hold


## 消息排序的方法

消息排序与发送者无关，仅仅依赖限制接收者接收的顺序。 

消息排序有：

+ FIFO order
+ Causal Order


#4. 用于消息排序的方法

## 4.1 Fixed Sequencer

## 4.2 Moving Sequencer

## 4.3 Privilege-Based

## 4.4 Communication History

## 4.5 Destinations Agreement

## 4.6 Time-Free Versus Time-Based Ordering

# 5. 与失败相关的问题

# 6. 用于容错的方法

## 6.1 错误检测
## 6.2 Group Membership Service
## 6.3 Resilient Communication Patterns
## 6.4 Message Stability
## 6.5 Consensus

截止到目前已经描述的方法都是容错全序广播依赖的底层方法；用于容错全序广播的另外一个选择是依赖更高层次的方法来解决这些问题。 可以通过将全序广播归纳为共识问题（solve total order broadcast by reducing it to a consensus problem)。这种方式下，容错，包括错误检测、消息稳定性检测 都包含在共识抽象中了。 



