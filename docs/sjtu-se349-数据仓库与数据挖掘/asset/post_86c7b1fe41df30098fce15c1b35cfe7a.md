
## （3）Structure data, graphs, social networks and information networks
图和网状数据

- The Spread of Behavior in an Online Social Network Experiment
  — http://www.sciencemag.org/cgi/content/abstract/329/5996/1194

## 行为以及信息传播和网络拓扑结构的关系

— 规则网络（如下面左侧）比小世界网络（如下面右侧）中行为传播的范围要更大，速度也要更快。这个结论和我们一般认为的：小世界网络具有捷径以及弱链接具有强作用，因而小世界网络比规则网络的信息传播快相反，而和行为需要多次（社会性的）强化的假设相一致。文中认为信息扩散和疾病传播属于接触传染，因此更依赖于拓扑；而“行为”不属于接触传染，而更依赖于养成。

— 作者首先将网络中的某一个人设为起点，然后系统给它直接接触的节点发邮件让他们从事某项健康活动，他们如果愿意参与该项健康活动，那么系统就再给他们的邻居发邮件邀请他们参加活动，进而让这个活动继续下去。因为规则网络中邻居之间的联系是紧密的，因此这个网络中一个用户一般会被它周围的邻居多次邀请，因此强化了他们参加的意愿。而小世界网络中，由于信息的传播不集中（信息扩散的快，不代表参与的人多），因此一开始单个用户被邀请的次数会偏少，行为强化次数较少，因此参加活动的意愿低。

![](img/6d25e92eb0bd56a22c311279c19b06b4_161_0.png)

## Structure and Network Analysis
结构和网络分析

- **Graph mining 图形挖掘**
  — Finding frequent subgraphs (e.g., chemical compounds), trees (XML), substructures (web fragments)
  寻找频繁子图（e.g., 化合物），树（XML）,子结构（web片段）

- **Web mining Web挖掘**
  — Web is a big information network: from PageRank to Google
  Web是一个巨大的信息网：从页面等级到谷歌

- **Analysis of Web information networks 情报网的分析**
  - Web community discovery, opinion mining, usage mining, ...
  Web社区的发现，意见挖掘，使用挖掘，...

## Structure and Network Analysis(Cont.)
结构和网络分析

### Information network analysis 情报网分析

- **Social networks: actors (objects, nodes) and relationships (edges)**
  社交网络：参与者（对象，结点）和关系（边）
  - e.g., author networks in CS, terrorist networks
    计算机科学的作者网络，恐怖分子网络

- **Multiple heterogeneous networks 多个异构网络**
  - A person could be multiple information networks: friends, family, classmates, …
    一个人有多个信息网：朋友，家庭，同学，…

- **Links carry a lot of semantic information: Link mining**
  链接携带着许多语义信息：链接挖掘

## （4）Spatial data and spatiotemporal data
空间和时间数据

![](img/6d25e92eb0bd56a22c311279c19b06b4_164_0.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_164_1.png)

Spatio-Temporal Data
Average Monthly Temperature of land and ocean

## （5）Multimedia database
多媒体数据

- 多媒体数据库主要包括图形(graphics)、图像(image)、声音(audio)、视频(video)等等，现代数据库技术一般将这些多媒体数据以二进制大对象的形式进行存储

- 对于多媒体数据库的数据挖掘，需要将存储和检索技术相结合。目前的主要方法包括构造多媒体数据立方体、多媒体数据库的多特征提取和基于相似性的模式匹配。

![](img/6d25e92eb0bd56a22c311279c19b06b4_165_0.png)

## （6）Document Data and The World-Wide Web
文本数据库和万维网(WWW)

- 文本数据库存储的是对对象的文字性描述。

- 文本数据库的分类
  — 无结构类型（大部分的文本资料和网页）
  — 半结构类型（XML数据）
  — 结构类型（图书馆数据）

- 万维网(WWW)可以被看成最大的文本数据库

- 数据挖掘内容
  — 内容检索
  — WEB访问模式检索

Each document becomes a ‘term’ vector,
- each term is a component (attribute) of the vector,
- the value of each component is the number of times the corresponding term occurs in the document.

|  | team | coach | play | ball | score | game | win | lost | timeout | season |
|---|---|---|---|---|---|---|---|---|---|---|
| Document 1 | 3 | 0 | 5 | 0 | 2 | 6 | 0 | 2 | 0 | 2 |
| Document 2 | 0 | 7 | 0 | 2 | 1 | 0 | 0 | 3 | 0 | 0 |
| Document 3 | 0 | 1 | 0 | 0 | 1 | 2 | 2 | 0 | 3 | 0 |

## Chapter 1. Introduction 引言

- Why Data Mining
- What is Data Mining
- What kinds of Data
- What kinds of Patterns
- What kinds of Technologies
- What kinds of Application
- Major Issues
- Summary

- 为什么进行数据挖掘？
- 什么是数据挖掘？
- 可以挖掘什么类型的数据？
- 可以挖掘什么类型的模式？
- 使用什么技术？
- 面向什么类型的应用？
- 数据挖掘的主要问题
- 小结

## One of Data Mining Functions: Generalization

## 数据挖掘模式：泛化（数据立方体是一种多维数据泛化）

## 数据泛化

- 通过把相对细的值（例如，属性年龄的数值）用较高层概念（如，青年、中年和老年）替换来汇总数据，或通过减少维数，在涉及较少维数的概念空间汇总数据（例如，在汇总学生组群时，删除生日和电话号码属性）。
- 给定存储在数据库中的大量数据，能够以简洁的形式在更一般的（而不是在较低的）抽象层描述数据是很有用的。允许数据集在多个抽象层泛化，便于用户考察数据的一般性质。

## 概念描述

- 一种泛化形式
- 概念通常指数据的汇集，如 frequent_buyers。概念描述不是数据的简单枚举，概念描述产生数据的特征和概括统计（必须所描述的概念所指的一些对象时，也称为类描述）
- 数据特征化：提供给定数据集的一般特性或特征的汇总。
  - 例：对AllElectronic公司的“大客户”（年消费额$1000以上）的特征化描述：40—50岁，有固定职业，信誉良好，等等
  - 数据特征化输出可以用多种形式提供，例如饼图、条图、多维数据立方体等
- 数据区分：概念或类的比较。提供两个或多个数据集的比较描述，将目标类数据对象的一般特性与一个或多个对比类对象的一般特性进行比较
  - 上一年销售增加30%的软件产品同期销售至少下降30%的软件产品进行比较
  - 例，AllElectronic公司（每月多于2次，或80%在20—40岁间，大学学历；非常客户（每年至少3次）中60%或者年龄大或者太年轻，没有大学学历）

| Status | Birth_country | Age_range | Gpa | Count |
|---|---|---|---|---|
| Graduate | Canada | 25-30 | Good | 90 |
| Undergraduate | Canada | 25-30 | Good | 210 |
