
## 数据的描述特征

## 3.3 数据清理

### 数据清理任务（Data cleaning tasks）

- 填补空值
- 识别孤立点、平滑噪声数据
- 纠正不一致数据
- 解决因集成带来的冗余

- 噪声数据：采用数据平滑技术
  - 分箱：通过考察“邻居”来平滑数据
    - 数据被分布到一些“桶”或箱中
    - 按箱平均值平滑、按箱边界平滑、按箱中值平滑等
    - Sorted data for price (in dollars): 4, 8, 9, 15, 21, 21, 24, 25, 26, 28, 29, 34
    - Partition into (equi-depth) bins:
      - Bin 1: 4, 8, 9, 15
      - Bin 2: 21, 21, 24, 25
      - Bin 3: 26, 28, 29, 34
    - Smoothing by bin means:
      - Bin 1: 9, 9, 9, 9
      - Bin 2: 23, 23, 23, 23
      - Bin 3: 29, 29, 29, 29
    - Smoothing by bin boundaries:
      - Bin 1: 4, 4, 4, 15
      - Bin 2: 21, 21, 25, 25
      - Bin 3: 26, 26, 26, 34
  - 聚类：将相近数据放入同一个簇中

![](img/76d573223e44fade1c0950849390a4b3_90_0.png)

  - 其它数据平滑技术：计算机和人工检查结合

![](img/76d573223e44fade1c0950849390a4b3_91_0.png)

- 不一致数据
  - 人工纠正

![](img/76d573223e44fade1c0950849390a4b3_92_0.png)

## 3.4 数据集成和变换

### Data Integration

- 数据集成：combines data from multiple sources into a coherent store
- 模式集成
  - 集成不同数据源上的元数据
  - 实体识别问题：
    - 一个数据库中的 cust-id 和另一个数据库中的 B.cust 是否指的是同一个实体。
    - 例如，family name vs. surname
- 语义异构：发现和解决数据值的冲突问题
  - 对于同一个实体，在不同的数据源中具有不同的值，如度量单位；175cm vs. 1.75m
  - 原因：基于不同的表示方式、度量单位或编码等

### 数据集成中的冗余处理

- 可能存在的冗余情况
  - 同一个属性在不同数据源中具有不同的值
  - 某一个属性可以由其它属性“导出”
  - 一些元组是重复的

### 数据变换

- 平滑
  - 去掉数据中的噪声
- 聚集
  - 对数据进行汇总和聚集
- 数据概化
  - 使用概念分层，用高层次概念替换低层次“原始”数据

## 3.5 数据约简

### Data Reduction Strategies

- 数据仓库通常存储T级数据
  - Complex data analysis/mining may take a very long time to run on the complete data set
- 数据约简的目的
  - Obtain a reduced representation of the data set that is much smaller in volume but yet produce the same (or almost the same) analytical results
- 数据约简策略
  - Data cube aggregation
  - 维归约：删除不相关的属性
  - 数据压缩
  - 数值压缩：用替代的较小的数据表示替换或估计数据，如抽样等
  - 离散化或概念分层产生

![](img/76d573223e44fade1c0950849390a4b3_99_0.png)

## 3.6 离散化和概念分层生成

### Discretization

- 三类属性
  - Nominal — values from an unordered set
    - categorical
  - Ordinal — values from an ordered set
  - Continuous — real numbers
- Discretization:
  - divide the range of a continuous attribute into intervals
  - Interval labels can then be used to replace actual data values
  - 减少给定连续属性值的个数

### 分类数据的概念分层

- 由用户或专家在模式级显式地说明属性的部分序
- 通过显式数据分组说明分层结构的一部分
- 说明属性集，但不说明它们的偏序。由系统自动产生属性的序，构造有意义的概念分层。
- 只说明部分属性集：语义密切相关的属性能够捆在一起。

| country | 15 distinct values |
| province_or_state | 65 distinct values |
| city | 3567 distinct values |
| street | 674,339 distinct values |

## 第五章：关联规则挖掘

### Outline

- 5.1 基本概念
- 5.2 经典挖掘方法
- 5.3 其它方法

### 5.1 基本概念

What is association rule mining?

Association rule mining searches for interesting relationships among items in a given data set.

一个典型的例子：购物篮分析

通过发现顾客放入购物篮中不同商品之间的联系，分析顾客的购买习惯，帮助销售商制定营销策略。

例如：顾客购买牛奶，也购买面包的可能性有多大？

### 购物篮信息

| cardid | cookies | fish | orange juice | lemon tea | red wine | peanuts | beer | chocolate milk | bread | vegetable |
|---|---|---|---|---|---|---|---|---|---|---|
| 39808 | cookies |  |  |  |  |  |  | chocolate milk | bread |  |
| 67362 | cookies |  |  |  |  |  |  |  | bread |  |
| 10872 |  | fish |  |  | red wine | peanuts | beer |  |  |  |
| 26748 |  |  |  | lemon tea |  |  |  | chocolate milk |  |  |
| 91609 |  |  |  |  |  |  |  |  |  |  |
| 26630 |  | fish |  | lemon tea |  |  |  |  | bread |  |
| 62995 |  |  | orange juice |  |  |  |  |  |  | vegetable |
| 38765 |  |  |  |  | red wine |  |  |  |  |  |
| 28935 |  |  |  |  |  | peanuts |  |  |  | vegetable |
| 41792 |  | fish |  |  |  |  |  |  |  | vegetable |
| 59480 |  | fish |  | lemon tea |  |  | beer | chocolate milk | bread | vegetable |
| 60755 |  | fish |  |  |  |  |  |  |  | vegetable |
| 70998 |  | fish |  |  |  | peanuts |  | chocolate milk |  |  |
| 80617 |  | fish | orange juice |  |  |  |  |  |  |  |
| 61144 |  | fish | orange juice |  |  |  |  | chocolate milk |  |  |
| 36405 |  |  | orange juice |  | red wine | peanuts |  |  |  |  |
| 76567 |  | fish |  |  |  |  | beer |  |  | vegetable |
| 85699 |  | fish |  |  |  |  |  |  |  |  |
| 11357 |  | fish |  |  | red wine |  |  |  |  |  |
| 97761 | cookies | fish |  | lemon tea |  |  | beer |  |  | vegetable |
| 20362 |  | fish |  |  |  | peanuts |  |  |  |  |
| 33173 | cookies |  |  | lemon tea |  |  |  |  |  |  |
| 69934 |  | fish |  |  |  |  |  |  |  |  |
| 14743 |  |  |  | lemon tea | red wine | peanuts | beer | chocolate milk | bread | vegetable |
| 83071 | cookies |  |  |  | red wine |  |  |  |  |  |
| 17571 |  |  |  |  | red wine | peanuts |  | chocolate milk |  | vegetable |
| 37917 | cookies |  |  | lemon tea |  |  |  |  | bread |  |
