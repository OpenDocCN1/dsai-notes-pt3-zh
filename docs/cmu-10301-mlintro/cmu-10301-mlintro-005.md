# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p05 Lecture_5_KNNs_&_Model_Selection.zh_en -BV1Z2cUefE4A_p5-

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_1.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_3.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_4.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_6.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_7.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_9.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_11.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_12.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_14.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_15.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_17.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_18.png)

## 1. 引言

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_20.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_22.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_23.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_25.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_27.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_28.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_29.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_30.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_32.png)

大家好，今天我们将继续讨论KNN算法。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_34.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_35.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_37.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_38.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_39.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_41.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_42.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_44.png)

## 2. KNN算法概述

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_46.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_48.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_50.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_52.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_53.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_54.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_55.png)

KNN算法是一种基于距离的监督学习算法，它通过计算新数据点与训练数据点之间的距离来预测新数据点的标签。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_57.png)

**公式**： \(d(x, y) = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2 + ... + (x_n - y_n)^2}\)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_59.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_61.png)

## 3. KNN算法的决策边界

KNN算法的决策边界是由距离最近的K个邻居决定的。如果K为奇数，则新数据点的标签将与最近的邻居相同；如果K为偶数，则新数据点的标签将与最近的邻居的多数标签相同。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_63.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_65.png)

## 4. KNN算法的优缺点

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_67.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_68.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_70.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_71.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_73.png)

**优点**：

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_75.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_76.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_77.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_78.png)

* 简单易懂
* 不需要训练时间
* 可以处理非线性数据

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_80.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_82.png)

**缺点**：

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_84.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_86.png)

* 计算量大
* 对噪声数据敏感
* 难以解释

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_88.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_90.png)

## 5. KNN算法的参数选择

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_92.png)

KNN算法的主要参数是K，它表示用于预测新数据点标签的邻居数量。

**公式**： \(k = \text{选择K个最近的邻居}\)

## 6. KNN算法的模型选择

KNN算法是一种非参数模型，它没有参数需要学习。因此，模型选择主要涉及选择合适的K值。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_94.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_96.png)

**代码**：

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_97.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_99.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_101.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_103.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_105.png)

```python
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_107.png)

# 分割数据集
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 创建KNN模型
knn = KNeighborsClassifier(n_neighbors=5)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_109.png)

# 训练模型
knn.fit(X_train, y_train)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_111.png)

# 预测测试集
y_pred = knn.predict(X_test)
```

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_113.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_115.png)

## 7. 总结

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_117.png)

本节课中，我们学习了KNN算法的基本原理、决策边界、优缺点以及参数选择。KNN算法是一种简单易懂的算法，但它对噪声数据敏感，并且计算量大。在实际应用中，需要根据具体问题选择合适的K值。

## 8. 下节课预告

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_119.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_121.png)

下节课我们将学习感知器算法。