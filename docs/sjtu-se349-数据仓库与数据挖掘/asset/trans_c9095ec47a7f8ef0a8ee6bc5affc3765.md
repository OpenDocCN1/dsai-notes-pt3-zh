

## 参考文献（3）
- S. Papadimitriou, H. Kitagawa, P. B. Gibbons, 和 C. Faloutsos. Loci：使用局部相关性积分进行快速离群点检测。*ICDE'03*
- A. Patcha 和 J.-M. Park. 异常检测技术概述：现有解决方案与最新技术趋势。*Comput. Netw.*, 51, 2007.
- X. Song, M. Wu, C. Jermaine 和 S. Ranka. 条件异常检测。*IEEE Trans. on Knowl. and Data Eng.*, 19, 2007.
- Y. Tao, X. Xiao 和 S. Zhou. 在任意度量空间中从大型数据库挖掘基于距离的离群点。*KDD'06*
- N. Ye 和 Q. Chen. 基于卡方统计量的异常检测技术，用于检测信息系统的入侵。*Quality and Reliability Engineering International*, 17:105–112, 2001.
- B.-K. Yi, N. Sidiropoulos, T. Johnson, H. V. Jagadish, C. Faloutsos 和 A. Biliris. 协同演化时间序列的在线数据挖掘。*ICDE'00*

## 离群点发现：统计方法

![](img/6d25e92eb0bd56a22c311279c19b06b4_1455_0.png)

假设存在一个生成数据集的底层分布模型
（例如正态分布）

- 使用不一致性测试，具体取决于
  - 数据分布
  - 分布参数（例如均值、方差）
  - 预期离群点的数量

- 缺点
  - 大多数测试仅针对单一属性
  - 在许多情况下，数据分布可能未知

## 离群点发现：基于距离的方法

- 引入该方法的目的是克服统计方法的主要局限性
  - 我们需要在未知数据分布的情况下进行多维分析
- 基于距离的离群点：DB(p, D)-离群点是指数据集 T 中的对象 O，使得 T 中至少有比例 p 的对象与 O 的距离大于 D
- 用于挖掘基于距离的离群点的算法 [Knorr & Ng, VLDB'98]
  - 基于索引的算法
  - 嵌套循环算法
  - 基于单元的算法

## 基于密度的局部离群点检测

- M. M. Breunig, H.-P. Kriegel, R. Ng, J. Sander. LOF：识别基于密度的局部离群点。SIGMOD 2000.
- 基于距离的离群点检测基于全局距离分布
- 如果数据分布不均匀，该方法在识别离群点时将会遇到困难
- 例如，C₁ 包含 400 个松散分布的点，C₂ 包含 100 个紧密聚集的点，以及 2 个离群点 o₁、o₂
- 基于距离的方法无法将 o₂ 识别为离群点

- 需要引入局部离群点的概念
- 局部离群因子（LOF）
  - 假设离群点并非精确判定
  - 每个点都有一个 LOF

![](img/6d25e92eb0bd56a22c311279c19b06b4_1457_0.png)

## 离群点发现：基于偏差的方法

- 通过检查组中对象的主要特征来识别离群点
- 与该描述“偏离”的对象被视为离群点
- 序列异常技术
  - 模拟人类从一系列假定相似的对象中区分出异常对象的方式
- OLAP 数据立方体技术
  - 使用数据立方体识别大型多维数据中的异常区域

## 参考文献（1）
- B. Abraham 和 G.E.P. Box. 时间序列中一些离群点问题的贝叶斯分析。*Biometrika*, 1979.
- Malik Agyemang, Ken Barker 和 Rada Alhajj. 数值与符号离群点挖掘技术综合综述。*Intell. Data Anal.*, 2006.
- Deepak Agarwal. 在交叉分类流中检测异常：一种贝叶斯方法。*Knowl. Inf. Syst.*, 2006.
- C. C. Aggarwal 和 P. S. Yu. 高维数据的离群点检测。*SIGMOD'01*.
- M. M. Breunig, H.-P. Kriegel, R. T. Ng 和 J. Sander. Optics-of：识别局部离群点。*PKDD '99*
- M. M. Breunig, H.-P. Kriegel, R. Ng 和 J. Sander. LOF：识别基于密度的局部离群点。*SIGMOD'00*.
- V. Chandola, A. Banerjee 和 V. Kumar. 异常检测：综述。*ACM Comput. Surv.*, 2009.
- D. Dasgupta 和 N.S. Majumdar. 使用负选择算法进行多维数据异常检测。*Computational Intelligence*, 2002.
- E. Eskin, A. Arnold, M. Prerau, L. Portnoy 和 S. Stolfo. 无监督异常检测的几何框架：检测未标记数据中的入侵。载于 Proc. 2002 Int. Conf. of Data Mining for Security Applications, 2002.
- E. Eskin. 使用学习到的概率分布在噪声数据上进行异常检测。*ICML'00*.
- T. Fawcett 和 F. Provost. 自适应欺诈检测。*Data Mining and Knowledge Discovery*, 1997.
- R. Fujimaki, T. Yairi 和 K. Machida. 使用核特征空间解决航天器异常检测问题的方法。*KDD '05*
- F. E. Grubbs. 检测样本中离群观测值的程序。*Technometrics*, 1969.

