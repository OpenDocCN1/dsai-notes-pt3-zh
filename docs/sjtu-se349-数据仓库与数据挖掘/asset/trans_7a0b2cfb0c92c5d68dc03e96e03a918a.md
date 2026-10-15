

## 2. Classification and regression analysis
数据挖掘模式之二：分类与回归

+   决策树是一个类似树形结构的流程图，每个内部节点表明在一个属性上的测试，树枝描述测试结果，叶子节点指明分类或分类的分布情况

+   决策树分类技术研究节点集的选择，节点的次序，门限值的确定公式等等，其目的是使分类比较准确，比较快

![](img/6d25e92eb0bd56a22c311279c19b06b4_179_0.png)

数据挖掘模式之二：分类与回归

+   - **分类**预测类别（离散的、无序的）标号
+   - **回归**建立连续值函数模型，用来预测缺失的或难以获得的数值数据值，而不是（离散）类标号

(1) 输入：训练数据集

| 姓名 | 职称 | 工龄 | 成果计分 | 家庭人口 | 身高 | 体重 | 应住房面积 |
|---|---|---:|---:|---:|---:|---:|---:|
| 张三 | 高工 | 25 | 5 | 3 | 1.7 | 80 | 85 |
| 李四 | 助工 | 20 | 4 | 4 | 1.7 | 85 | 75 |
| 王五 | 助工 | 10 | 1 | 2 | 1.8 | 65 | 50 |
| 张 C | 高工 | 25 | 3 | 2 | 1.7 | 80 | 75 |
| 李 D | 高工 | 30 | 6 | 3 | 1.7 | 85 | 85 |
| 王 E | 高工 | 20 | 5 | 5 | 1.8 | 65 | 70 |

+   (2) 输出从训练数据中“发现”一个分房计分公式（知识）
+   
+   (3) 调用特征选择过程。比较张三与张 C，李四与李 D，王五与王 E 发现身高、体重与住房无关，删去
+   
+   (4) 交互生成加权机制——Σ PiFi。其中 Fi 为各条件量化值，Pi 为加权值，总分为应住房面积
+   
+   (5) 根据训练数据，调整加权。张三与张 C 以及类似与张三条件的应住 85 平方米等等，使得在训练集中各记录的 Σ PiFi，刚好在应住房面积的分数段中
+   
+   (6) 用测试数据测试和修改公式 Total = Σ PiFi
+   
+   (7) 公式 Total = Σ PiFi 就是从数据中“挖”出来的分类知识，可以推广使用

## 3. Cluster Analysis
数据挖掘模式之三：聚类分析

聚类与分类明显不同之处在于学习样本（数据）类别是否已知

+   ✓ 分类：监督式学习 Group data to form new categories (i.e., clusters)
+   ✓ 聚类：非监督式学习 Unsupervised learning (i.e., Class label is unknown)

Principle: Maximizing intra-class similarity & minimizing interclass similarity

+   ✓ 原则：最大化类内相似性 & 最小化类间相似性

Intracluster distances are minimized

Intercluster distances are maximized

+   1) 含k字段的记录<---> K维空间一点。
+   2) 对各维施加权，构造k维空间的距离公式，如最简单的欧氏空间距离(Σ ΔXi²)1/2。
+   3) 被分类对象视为k维星云，以距离原则分为星系或星团。
+   4) 不同考察角度，不同距离公式，不同聚类结果。

## 3. Cluster Analysis
数据挖掘模式之三：聚类分析

+   - Clustering Points: 3204 Articles of Los Angeles Times.
+   - Similarity Measure: How many words are common in these documents (after some word filtering).

| Category | Total Articles | Correctly Placed |
|---|---|---|
| Financial | 555 | 364 |
| Foreign | 341 | 260 |
| National | 273 | 36 |
| Metro | 943 | 746 |
| Sports | 738 | 573 |
| Entertainment | 354 | 278 |

![](img/6d25e92eb0bd56a22c311279c19b06b4_183_0.png)

+   - 给出的新闻文章可以根据它们各自的主题分组
+   - 每篇文章表示为词-频率对(w,c)的集合，其中w是词，而c是该词在文章中出现的次数。一个好的聚类算法应当能够根据文章中出现的词的相似性，进行主题分组。
+   - 在该数据集中，有两个自然簇
+     — 第一个簇由前四篇文章组成，对应于经济新闻，而第二个族包含后四篇文章，对应于卫生保健新闻。

## 4. Outlier Analysis
数据挖掘模式之四：离群点分析

# Outlier analysis 离群点分析

+   Outlier: A data object that does not comply with the general behavior of the data
+   离群点：与数据的一般行为不一致的数据对象

+   Noise or exception? 噪声或者异常？
+   大部分数据挖掘方法都将离群点看做噪声或者异常而丢弃

+   “One person’s garbage could be another person’s treasure”
+   一个人的垃圾可能是另一个人的宝藏

+   Application: Useful in fraud detection, rare events analysis
+   应用：在欺诈侦测，罕见事件分析中十分有用

![](img/6d25e92eb0bd56a22c311279c19b06b4_184_0.png)

## 问题一：所有模式都是有趣的吗？

+   - 数据挖掘可能产生数以千计的模式或规则，但并不是所有的模式或规则都是令人感兴趣的。

+   - 模式兴趣度的度量：一个模式是有趣的，如果
+     - （1）它易于被人理解；
+     - （2）在某种程度上，对于新的或测试数据是有效的；
+     - （3）具有潜在效用；
+     - （4）新颖的；
+     - （5）符合用户确信的某种假设

+   - 有趣的模式代表知识

## 问题一：所有模式都是有趣的吗？

+   模式兴趣度的客观和主观度量
+   — 客观度量: 基于所发现模式的结构和关于它们的统计，比如：支持度、置信度等等
+   置信度可以用条件概率表示，即包含X的事务也包含Y的概率
+   — 主观度量: 基于用户对数据的判断。比如：出乎意料的、新颖的、可行的等等

support(X⇒Y) = P(X ∪ Y)

confidence(X⇒Y) = P(Y | X)

置信度可以用条件概率表示，即包含X的事务也包含Y的概率

## 问题三：数据挖掘能够仅仅产生有趣的模式吗？

+   - 这是数据挖掘的优化问题。
+   - 对于数据挖掘系统，仅产生有趣的模式是非常期望的。
+     这对于用户和数据挖掘系统都更加有效，因为这样就不需要搜遍所产生的模式来识别真正有趣的模式。
+   - 在这方面已经有了一些进展。然而，在数据挖掘中这种优化仍然是个挑战。

## Chapter 1. Introduction 引言

+   - Why Data Mining
+   - What is Data Mining
+   - What kinds of Data
+   - What kinds of Patterns
+   - What kinds of Technologies
+   - What kinds of Application
+   - Major Issues
+   - Summary

+   - 为什么进行数据挖掘？
+   - 什么是数据挖掘？
+   - 可以挖掘什么类型的数据？
+   - 可以挖掘什么类型的模式？
+   - 使用什么技术？
+   - 面向什么类型的应用？
+   - 数据挖掘的主要问题
+   - 小结

## Data Mining: Confluence of Multiple Disciplines
多学科的交叉

![](img/6d25e92eb0bd56a22c311279c19b06b4_190_0.png)

