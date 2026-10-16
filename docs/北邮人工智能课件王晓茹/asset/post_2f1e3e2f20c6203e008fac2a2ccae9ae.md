
## OPTICS: Some Extension from DBSCAN

OPTICS算法是对DBSCAN算法的改进，因为在DBSCAN算法中需要用户设定ε-邻域和MinPts，但是在实际应用中用户往往很难确定这些参数，而且这些参数设置的不同往往会导致聚类结果有很大差别。

![](img/806dfb586cd1a39120c0a828715591b9_79_0.png)

## Density-Based Clustering: OPTICS & Its Applications

![](img/806dfb586cd1a39120c0a828715591b9_79_1.png)

## DENCLUE: Using Statistical Density Functions

DENCLUE算法的依据是某个数据点在邻域内的影响可以用一个数学函数来形式化地表达，这个函数为影响函数。被聚类数据空间的整体密度函数是所有数据点影响函数的总和。在聚类时就根据全局密度函数的局部最大值，即密度吸引子点来确定。

- DENsity-based CLUstEring by Hinneburg & Keim (KDD’98)
- Using statistical density functions:
  - 影响函数及整体密度函数公式
- Major features
  - Solid mathematical foundation
  - Good for data sets with large amounts of noise
  - Allows a compact mathematical description of arbitrarily shaped clusters in high-dimensional data sets
  - Significantly faster than existing algorithm (e.g., DBSCAN)
  - But needs a large number of parameters

## Denclue: Technical Essence

- Influence function: describes the impact of a data point within its neighborhood
- Overall density of the data space can be calculated as the sum of the influence functions of all data points
- Clusters can be determined mathematically by identifying density attractors
- Density attractors are local maxima of the overall density function

## Density Attractor

![](img/806dfb586cd1a39120c0a828715591b9_79_2.png)

## Center-Defined and Arbitrary

![](img/806dfb586cd1a39120c0a828715591b9_79_3.png)

## 九、网格聚类

- 将对象空间量化为有限数目的单元，形成一个网格结构，所有的聚类都在这个网格结构中进行。
- 其优点是处理速度很快，其处理时间不取决于数据的数目，只与量化空间中每一维的单元数目有关。

在网格聚类方法中，有利用存储在小格单元中的统计信息进行聚类的STING算法、利用小波变换方法进行聚类的WaveCluster方法，以及在高维数据空间基于网格和密度的聚类方法。

### STING算法

STING算法的主要优点是效率高，通过对数据集的一次扫描来计算单元的统计信息，因此产生聚类的时间复杂度是O(n)。在建立层次结构以后，查询的时间复杂度是O(g)，g远小于n。STING算法采用网格结构，有利于并行处理和增量更新。

STING（Statistical Information Grid-based method）是一种基于网格的多分辨率聚类技术，它将空间区域划分为矩形单元。针对不同的分辨率，通常在多个级别形成矩形单元，这些单元形成了一个层次结构。每一级的每个单元被划分为多个下一层的单元。高层单元的统计参数可以很轻松地从底层单元的统计参数得到。这些参数包括与数据无关的参数count、与属性相关的参数m（平均值）、s（标准差）、min（最小值）、max（最大值），以及该单元中属性值的分布类型。STING算法采用了一种多分辨率层次结构进行聚类分析，该聚类算法的顶层采用粗粒度网格的最近邻聚类。如果粒度比较细，处理的代价会显著增加；如果粒度较粗，则聚类质量会受到影响。

### CLIQUE算法

基于网格和密度的聚类CLIQUE算法主要步骤：

- （1）将数据空间划分为互不相交的长方形单元，记录每个单元中的对象数。
- （2）用先验性质识别包含簇的子空间。
- （3）在感兴趣的子空间中先找出密集单元，再找出相连接的密集单元，以识别簇。
- （4）为每个簇生成最小化的描述。

### WaveCluster方法

- WaveCluster方法首先通过在数据空间上强加一个多维网格结构来汇总数据，每个网格单元汇总了一组映射到该单元中的点的信息，然后采用一种小波变换对原始数据进行变换，重点信息在进行小波变换时使用，变换后在变换空间中集中到类区域。
- 小波变换的聚类是无监督聚类，不用事先假设聚类的形状，可以发现任意形状的聚类，边界弱信号不会被屏蔽，可以剔除孤立点，本身运算开销不大。

## Summary

- Cluster analysis groups objects based on their similarity and has wide applications
- Measure of similarity can be computed for various types of data
- Clustering algorithms can be categorized into partitioning methods, hierarchical methods, density-based methods, grid-based methods, and model-based methods
- Outlier detection and analysis is very useful for fraud detection, etc. and can be performed by statistical, distance-based or deviation-based approaches
- There are still lots of research issues on cluster analysis

## 第一章 概述

- 人工智能及发展
- 研究基础内容
- 研究领域

人工智能（Artificial Intelligence AI）

研究如何在机器上实现人类智能的学科。

### 不同定义

- （1）人工智能是指由计算机实现的人造智能。人工智能就是用人工的方法在机器（计算机）上实现的智能。作为一门学科，人工智能可以定义为：人工智能是一门研究如何构造智能机器（智能计算机）或智能系统，使它能模拟、延伸、扩展人类智能的学科。（能力）
- （2）人工智能是一门交叉边缘学科，与人工智能有关的学科有：计算机科学、数学、哲学、语言学、神经生理学、神经心理学、脑科学、认知科学、逻辑学、控制论等（学科）
- 定义3 人工智能是一种使计算机能思维，使机器具有智力的激动人心的新尝试（Haugeland,1985）。
- 定义4 人工智能是与人的思维、决策、问题求解和学习等有关活动的自动化（Bellman,1978）。
- 定义5 人工智能是用计算模型研究智力行为（Charniak和McDermott,1985）。
- 定义6 人工智能是研究那些使理解、推理和行为成为可能的计算（Winston,1992）。
- 定义7 人工智能是一种能够执行需要人的智能的创造性机器的技术（Kurzweil,1990）。
- 定义8 人工智能研究如何使计算机做事让人过得更好（Rich和Knight,1991）。
- 定义9 人工智能是一门通过计算过程力图理解和模仿智能行为的学科（Schalkoff,1990）。
- 定义10 人工智能是计算机科学中与智能行为的自动化有关的一个分支（Luger和Stubblefield,1993）。

### 智能

有效获取、传递、处理、再生和利用信息，从而在任意给定的环境下达到预定目的的能力。

**智能特征：**

- 具有感知能力。通过视觉、听觉、触觉、味觉和嗅觉感知外部世界。
- 具有记忆与思维能力。记忆能存储由感知器官感知到的外部信息以及由思维所产生的知识。思维用于对记忆的信息进行处理。思维可分为逻辑思维和形象思维。
- 具有学习能力及自适应能力。
- 具有行为能力。

- 计算智能（能存会算）
- 感知智能（能听会说、能看会认）
- 认知智能（能理解会思考）

**相关学说：**

- **思维理论/认知科学：** 研究人们认识世界规律和方法的一门学科，在于揭开大脑思维功能的奥秘。
- **知识阈值理论：** 智能行为取决于知识数量及一般化的程度。

