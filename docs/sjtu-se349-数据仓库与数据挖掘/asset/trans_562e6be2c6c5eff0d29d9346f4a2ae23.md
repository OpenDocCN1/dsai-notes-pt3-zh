

## 属性构造（Feature Generation）

- 通过创建新的属性，以便比原始属性更有效地获取数据集中的重要信息
- 三种通用方法
  - 属性提取（Attribute extraction）
    - 特定领域（Domain-specific）
  - 将数据映射到新的空间（Mapping data to new space）（参见：数据规约）
    - 例如：傅里叶变换，小波变换
  - 属性构造（Attribute construction）
    - 属性合并（Combining features）
    - 数据离散化（Data discretization）

## 数据规约策略

- 维规约（Dimensionality reduction），例如，删除不重要的属性
  - 小波变换（Wavelet transforms）
  - 主成分分析（Principal Components Analysis，PCA）
  - 属性子集选择（Feature subset selection，feature creation）
- 数量规约（Numerosity reduction）（也称：数据规约 Data Reduction）
  - 回归（Regression）和对数-线性模型（Log-Linear Models）
  - 直方图（Histograms）、聚类（clustering）、抽样（sampling）
  - 数据立方体聚集（Data cube aggregation）
- 数据压缩（Data compression）

## 数据规约2：数量规约（Numerosity Reduction）

- 通过选择替代的、更小的数据形式来表示数据，从而减少数据量
- 参数化方法（Parametric methods）（例如，回归）
  - 使用模型估计数据，使得一般只需要存放模型参数，而不是实际数据（离群点可能也要存放）
  - 例：对数-线性模型（Log-linear models）
- 非参数方法（Non-parametric methods）
  - 不用模型估计
  - 包括：直方图（histograms）、聚类（clustering）、抽样（sampling）……

## 数据规约策略

- 维规约（Dimensionality reduction），例如，删除不重要的属性
  - 小波变换（Wavelet transforms）
  - 主成分分析（Principal Components Analysis，PCA）
  - 属性子集选择（Feature subset selection，feature creation）

- 数量规约（Numerosity reduction）（也称：数据规约 Data Reduction）
  - 回归（Regression）和对数-线性模型（Log-Linear Models）
  - 直方图（Histograms）、聚类（clustering）、抽样（sampling）
  - 数据立方体聚集（Data cube aggregation）

- 数据压缩（Data compression）

## 回归和对数线性模型：参数化数据规约

- 线性回归
  - 对数据建模，使之拟合到一条直线
  - 通常使用**最小二乘法（least-square method）**
- **多元回归（Multiple regression）**
  - 允许用两个或多个自变量的线性函数对因变量 Y 建模
- **对数线性模型（Log-linear model）**
  - 近似离散的多维概率分布

## 回归分析（Regression Analysis）

- **回归分析（Regression analysis）**：建模和分析由一个或多个自变量（亦称解释变量或预测变量）和一个因变量（也称为响应变量或测量值）组成的数值数据的技术总称
- 估计参数，以便提供对数据的“最佳拟合”
- 最常见、最合适的方法是通过使用最小二乘法估计的，但其它标准也被用于预测（包括时间序列数据的预测）、推理、假设检验和因果关系建模

![](img/6d25e92eb0bd56a22c311279c19b06b4_408_0.png)

## 回归分析和对数线性模型

- **线性回归（Linear regression）**：$Y = wX + b$
  - 回归系数 $w$ 和 $b$ 根据现有的数据进行估计
  - 根据已知 $Y_1, Y_2, \ldots, X_1, X_2, \ldots$ 使用最小二乘法

- **多元回归（Multiple regression）**：$Y = b_0 + b_1X_1 + b_2X_2$
  - 许多非线性函数可转化为上述公式

- **对数线性模型（Log-linear models）**：
  - 近似离散的多维概率分布
  - 给定 $n$ 维元组的集合，可以把每个元组看作 $n$ 维空间的点。使用对数线性模型，基于维组合的一个较小子集，估计多维空间中每个点的概率，使得高维空间可以由低维空间来构造
  - 可用于维规约和数据光滑

## 数据规约策略

- 维规约（Dimensionality reduction），例如，删除不重要的属性
  - 小波变换（Wavelet transforms）
  - 主成分分析（Principal Components Analysis，PCA）
  - 属性子集选择（Feature subset selection，feature creation）
- 数量规约（Numerosity reduction）（也称：数据规约 Data Reduction）
  - 回归（Regression）和对数-线性模型（Log-Linear Models）
  - 直方图（Histograms）、聚类（clustering）、抽样（sampling）
  - 数据立方体聚集（Data cube aggregation）
- 数据压缩（Data compression）

## 直方图分析（Histogram Analysis）

- 将数据划分为子集
- 分区规则：
  - 等宽（Equal-width）：桶区间范围相等
  - 等频（Equal-frequency，或等深度 equal-depth）

![](img/6d25e92eb0bd56a22c311279c19b06b4_411_0.png)

## 例 3.4 下面的数据是 AllElectronics 通常销售的商品的单价表（按$取整）。已对数据进行了排序：1, 1, 5, 5, 5, 5, 5, 5, 10, 10, 10, 10, 12, 14, 14, 14, 15, 15, 15, 15, 15, 15, 18, 18, 18, 18, 18, 18, 18, 18, 20, 20, 20, 20, 20, 20, 21, 21, 21, 21, 25, 25, 25, 25, 25, 28, 28, 30, 30, 30

图 3.9 使用单桶显示了这些数据的直方图。为进一步压缩数据，通常让一个桶代表给定属性的一个连续值域。在图 3.10 中每个桶代表 price 的一个不同的$10区间。

![](img/6d25e92eb0bd56a22c311279c19b06b4_412_0.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_412_1.png)

## 聚类（Clustering）

- 根据相似度，将数据集划分成簇，只记录簇的质心和直径
- 如果数据能够被聚类，则非常高效
- 可以进行层次聚类，并存储在多维索引树结构中
- 有许多聚类定义和算法可供选择
- 在第 10 章中将详细深入学习聚类算法

## 抽样（Sampling）

- 抽样（Sampling）：用小样本 *s* 来代表大数据集 *N*
- 挖掘算法的复杂度可能相对于数据大小是亚线性（sub-linear）的
- 主要准则：选出数据集中有代表性的子集
  - 简单随机抽样可能存在偏差，表现很差
  - 开发自适应采样方法，例如，分层抽样
- 注意：抽样方法可能不会减少数据库的读写

## 抽样种类

- 简单随机抽样（Simple random sampling）
  - 每个特定项被选中的概率相等
- 无放回简单随机抽样（Sampling without replacement）
  - 一旦某个对象被选中，它就从总体中移除
- 有放回简单随机抽样（Sampling with replacement）
  - 被选中的对象不会从总体中移除
- 簇抽样
- 分层抽样（Stratified sampling）：
  - 将数据集划分成多个部分，并从每个部分按比例（即大约相同的数据百分比）抽取样本
  - 与偏斜数据结合使用

