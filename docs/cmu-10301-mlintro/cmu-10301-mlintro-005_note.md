# 机器学习导论：05：K近邻算法与模型选择 👨‍🏫

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_1.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_3.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_4.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_6.png)

在本节课中，我们将要学习K近邻算法。这是一种基于实例的监督学习算法，它通过查找训练数据中与新数据点最相似的“邻居”来进行预测。我们将探讨其工作原理、优缺点以及如何选择合适的模型参数。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_7.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_9.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_11.png)

## 1. 引言 🎯

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_12.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_14.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_15.png)

上一节我们讨论了机器学习的基本概念。本节中，我们来看看一种非常直观且简单的分类与回归算法——K近邻算法。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_17.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_18.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_20.png)

KNN算法是一种基于距离的监督学习算法。它通过计算新数据点与训练数据点之间的距离来预测新数据点的标签。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_22.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_23.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_25.png)

## 2. KNN算法概述 📖

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_27.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_28.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_29.png)

KNN算法的核心思想是“物以类聚”。对于一个新数据点，算法会在训练集中找到距离它最近的K个数据点，然后根据这K个“邻居”的标签来决定新数据点的标签。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_30.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_32.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_34.png)

**公式**：计算两点间欧氏距离的公式为：
`d(x, y) = √[(x₁ - y₁)² + (x₂ - y₂)² + ... + (xₙ - yₙ)²]`

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_35.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_37.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_38.png)

## 3. KNN算法的决策边界 🗺️

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_39.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_41.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_42.png)

KNN算法的决策边界是由距离最近的K个邻居决定的。如果K为奇数，则新数据点的标签将与最近的邻居相同；如果K为偶数，则新数据点的标签将与最近的邻居的多数标签相同。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_44.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_46.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_48.png)

决策边界不是一条平滑的直线或曲线，而是由许多小区域拼接而成，形状取决于K值的大小。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_50.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_52.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_53.png)

## 4. KNN算法的优缺点 ⚖️

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_54.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_55.png)

了解一个算法的优缺点有助于我们在实际问题中做出合适的选择。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_57.png)

**优点**：
以下是KNN算法的主要优点：
*   **简单易懂**：原理直观，易于理解和实现。
*   **不需要训练时间**：模型本身不进行参数学习，只是存储训练数据。
*   **可以处理非线性数据**：决策边界可以非常复杂，适应各种数据分布。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_59.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_61.png)

**缺点**：
以下是KNN算法的主要缺点：
*   **计算量大**：预测时需要计算新数据点与所有训练数据点的距离。
*   **对噪声数据敏感**：如果近邻中存在错误标签，预测结果会受到影响。
*   **难以解释**：与决策树等模型相比，其预测逻辑不那么清晰。
*   **需要选择合适的K值**：K值的选择对模型性能影响很大。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_63.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_65.png)

## 5. KNN算法的参数选择 🔧

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_67.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_68.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_70.png)

KNN算法的主要参数是K，它表示用于预测新数据点标签的邻居数量。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_71.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_73.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_75.png)

**公式**： `k = 选择K个最近的邻居`

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_76.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_77.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_78.png)

K值的选择是一个权衡：
*   **K值较小**：模型更复杂，容易过拟合，对噪声敏感。
*   **K值较大**：模型更简单，决策边界更平滑，但可能忽略数据的局部特征。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_80.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_82.png)

## 6. KNN算法的模型选择 🤖

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_84.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_86.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_88.png)

KNN算法是一种非参数模型，它没有需要从数据中学习的内部参数。因此，模型选择主要涉及选择合适的K值以及距离度量方式。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_90.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_92.png)

在实际应用中，我们通常使用交叉验证等方法来选择最优的K值。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_94.png)

**代码**：
以下是使用Python的scikit-learn库实现KNN分类的基本步骤：
```python
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_96.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_97.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_99.png)

# 假设X是特征数据，y是标签数据
# 分割数据集为训练集和测试集
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_101.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_103.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_105.png)

# 创建KNN模型，设置邻居数K=5
knn = KNeighborsClassifier(n_neighbors=5)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_107.png)

# “训练”模型（实际上是存储数据）
knn.fit(X_train, y_train)

# 在测试集上进行预测
y_pred = knn.predict(X_test)
```

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_109.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_111.png)

## 7. 总结 📝

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_113.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_115.png)

本节课中我们一起学习了K近邻算法的基本原理。我们了解到，KNN通过查找最近邻来进行预测，其决策边界由K值决定。该算法简单直观且无需训练，但对计算资源要求高且对噪声敏感。在实际应用中，关键步骤是选择合适的K值以平衡模型的偏差和方差。

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_117.png)

## 8. 下节课预告 🔮

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_119.png)

![](img/3f7ed6a0e0ee8fb8842834310590ed0a_121.png)

下节课我们将学习另一种基础的线性分类器——感知器算法。我们将探讨它如何通过迭代更新权重来找到一个分离超平面。