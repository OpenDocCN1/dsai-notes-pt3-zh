
## 数据挖掘

北京邮电大学 计算机科学与技术学院

郑岩 副教授/博士后

yanzheng@bupt.edu.cn

2007.3

## 主要内容

- 1. 概述
- 2. 数据仓库与OLAP技术
- 3. 数据挖掘技术
- 4. 数据挖掘在电信领域的应用
- 5. 数据挖掘工具
- 6. 数据挖掘实例

## 1 概述

- 1.1 背景
- 1.2 数据挖掘定义
- 1.3 基本概念
- 1.4 主要功能
- 1.5 数据挖掘模型
- 1.6 实现流程
- 1.7 数据挖掘的应用
- 1.8 未来趋势

### 1.1 背景

二十世纪末以来，全球信息量以惊人的速度急剧增长—据估计，每二十个月将增加一倍。许多组织机构的IT系统中都收集了大量的数据（信息）。目前的数据库系统虽然可以高效地实现数据的录入、查询、统计等功能，但无法发现数据中存在的关系和规则，无法根据现有的数据预测未来的发展趋势。为了充分利用现有信息资源，从海量数据中找出隐藏的知识，数据挖掘技术应运而生并显示出强大的生命力。

数据挖掘是八十年代投资AI研究项目失败后，AI转入实际应用时提出的。它是一个新兴的，面向商业应用的AI研究。

1989年8月，在美国底特律召开的第11届国际人工智能联合会议的专题讨论会上首次出现数据库中的知识发现（Knowledge Discovery in Database, KDD）这一术语。

随后，在1991年、1993年和1994年都举行KDD专题讨论会，汇集来自各个领域的研究人员和应用开发者，集中讨论数据统计、海量数据分析算法、知识表示、知识运用等问题。最初，数据挖掘是作为KDD中利用算法处理数据的一个步骤，其后逐渐演变成KDD的同义词。

现在，人们往往不加区别地使用两者。KDD常常被称为数据挖掘（Data Mining），实际两者是有区别的。一般将KDD中进行知识学习的阶段称为数据挖掘（Data Mining），数据挖掘是KDD中一个非常重要的处理步骤。

数据挖掘是近年来出现的客户关系管理（Customer Relationship Management，CRM）、商业智能（Business Intelligence，BI）等热点领域的核心技术之一。

### 1.2 数据挖掘定义

Data Mining...

- Finding patterns in data
- Describing the patterns - one way is by rules
- Predicting from the rules - classification - forecasting

or

Knowledge Discovery in Databases

- Extracting knowledge
- Representing knowledge acquired
- Using the knowledge for future examples

- 技术角度的定义

数据挖掘（Data Mining）是从大量的、不完全的、有噪声的、模糊的、随机的实际应用数据中，提取隐含其中的、人们事先不知道的、但又是潜在有用的信息和知识的过程。与数据挖掘相近的同义词包括：数据融合、数据分析 and 决策支持等。

这一定义包括好几层含义：数据源必须是真实的、海量的、含噪声的；发现的是用户感兴趣的知识；发现的知识要可接受、可理解、可运用；并不要求发现放之四海皆准的知识，仅支持特定的发现问题。

- 商业角度的定义

数据挖掘是一种新的商业信息处理技术，其主要特点是对商业数据库中的大量业务数据进行抽取、转换、分析和其他模型化处理，从中提取辅助商业决策的关键性信息。

简言之，数据挖掘其实是一类深层次的数据分析方法。因此，数据挖掘可以描述为：按企业既定业务目标，对大量的企业数据进行探索和分析，揭示隐藏的、未知的或验证已知的规律性，并进一步将其模型化的有效方法。

## What Data?

- What sort of data?
- Consider here only textual type data
  - characters or numbers
- Data that has been structured in some way
- Data can also be be visual, aural or tactile
- Pattern recognition in other data
  - visual analysis of data – *later*

## Data sets

Data set concerning bridges in USA

```
E13,A,33,CRAFTS,HIGHWAY,?,2,N,THROUGH,WOOD,?,S,WOOD
E15,A,28,CRAFTS,RR,?,2,N,THROUGH,WOOD,?,S,WOOD
E16,A,25,CRAFTS,HIGHWAY,MEDIUM,2,N,THROUGH,IRON,MEDIUM,S-F,SUSPEN
E17,M,4,CRAFTS,RR,MEDIUM,2,N,THROUGH,IRON,MEDIUM,?,SIMPLE-T
E18,A,28,CRAFTS,RR,MEDIUM,2,N,THROUGH,IRON,SHORT,S,SIMPLE-T
E19,A,29,CRAFTS,HIGHWAY,MEDIUM,2,N,THROUGH,WOOD,MEDIUM,S,WOOD
E20,A,32,EMERGING,HIGHWAY,MEDIUM,2,N,THROUGH,WOOD,MEDIUM,S,WOOD
E21,M,16,EMERGING,RR,?,2,?,THROUGH,IRON,?,S,SIMPLE-T
E23,M,1,EMERGING,HIGHWAY,MEDIUM,?, ?,THROUGH,STEEL,LONG,F,SUSPEN
E22,A,24,EMERGING,HIGHWAY,MEDIUM,4,G,THROUGH,WOOD,SHORT,S,WOOD
E24,O,45,EMERGING,RR,?,2,G,?,STEEL,?, ?,SIMPLE-T
E25,M,10,EMERGING,RR,?,2,G,?,STEEL,?, ?,SIMPLE-T
E27,A,39,EMERGING,RR,?,2,G,THROUGH,STEEL,?,F,SIMPLE-T
E26,M,12,EMERGING,RR,MEDIUM,2,G,THROUGH,STEEL,MEDIUM,S,SIMPLE-T
E30,A,31,EMERGING,RR,?,2,G,THROUGH,STEEL,MEDIUM,F,SIMPLE-T
E29,A,26,EMERGING,HIGHWAY,MEDIUM,2,G,THROUGH,STEEL,MEDIUM,?,SUSPEN
E28,M,3,EMERGING,HIGHWAY,MEDIUM,2,G,THROUGH,STEEL,MEDIUM,S,ARCH
E32,A,30,EMERGING,HIGHWAY,?,2,G,THROUGH,IRON,MEDIUM,F,SIMPLE-T
E31,M,8,EMERGING,RR,MEDIUM,2,G,THROUGH,STEEL,MEDIUM,S,SIMPLE-T
E34,O,41,EMERGING,RR,LONG,2,G,THROUGH,STEEL,LONG,F,SIMPLE-T
E33,M,19,EMERGING,HIGHWAY,MEDIUM,?,3,G,THROUGH,IRON,MEDIUM,F,SIMPLE-T
E36,O,45,MATURE,HIGHWAY,?,2,G,THROUGH,IRON,SHORT,F,SIMPLE-T
E35,A,27,MATURE,HIGHWAY,MEDIUM,2,G,THROUGH,STEEL,MEDIUM,F,SIMPLE-T
E38,M,17,MATURE,HIGHWAY,?,2,G,THROUGH,IRON,MEDIUM,F,SIMPLE-T
E37,M,18,MATURE,RR,MEDIUM,2,G,THROUGH,STEEL,MEDIUM,S,SIMPLE-T
E39,A,25,MATURE,HIGHWAY,?,2,G,THROUGH,STEEL,MEDIUM,F,SIMPLE-T
E4,A,27,MATURE,AQUEDUCT,MEDIUM,1,N,THROUGH,WOOD,SHORT,S,WOOD
E40,M,22,MATURE,HIGHWAY,?,2,G,THROUGH,STEEL,MEDIUM,F,SIMPLE-T
E41,M,11,MATURE,HIGHWAY,?,2,G,THROUGH,IRON,MEDIUM,F,SIMPLE-T
E42,M,9,MATURE,HIGHWAY,LONG,2,G,THROUGH,STEEL,LONG,F,SIMPLE-T
```

![](img/97ec20d772baf04740a42252ab8f47d8_11_0.png)
