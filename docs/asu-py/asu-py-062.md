# 62：K最近邻算法 🧠

![](img/e364fa9e4347dee9913bb0c156837310_0.png)

![](img/e364fa9e4347dee9913bb0c156837310_2.png)

![](img/e364fa9e4347dee9913bb0c156837310_4.png)

在本节课中，我们将要学习 K最近邻算法。这是一种监督式机器学习算法，可用于分类和回归问题。我们将介绍其工作原理、适用场景，并通过一个实际案例演示如何构建和评估一个KNN模型。

![](img/e364fa9e4347dee9913bb0c156837310_5.png)

---

![](img/e364fa9e4347dee9913bb0c156837310_7.png)

## 什么是K最近邻算法？🤔

K最近邻算法是一种监督式机器学习算法。这意味着我们使用带有标签的数据来训练模型。该算法可用于解决分类和回归问题。

使用K最近邻算法时，一个主要假设是：当数据被绘制在图表上时，相似的数据点彼此距离很近。观察示例图像，我们可以看到距离相近的数据点被认为属于同一类别，而距离过远的数据点则被认为属于不同类别。本质上，对于每个数据点，我们希望根据其与其他数据点的接近程度来识别其类别。

![](img/e364fa9e4347dee9913bb0c156837310_9.png)

K最近邻算法查看样本之间的距离，这些样本也被称为“邻居”，并根据邻近性来区分样本的类别。

![](img/e364fa9e4347dee9913bb0c156837310_11.png)

以下代码展示了如何创建K最近邻模型，其中 `n_neighbors` 参数用于指定要考虑的邻居数量。

![](img/e364fa9e4347dee9913bb0c156837310_12.png)

![](img/e364fa9e4347dee9913bb0c156837310_14.png)

```python
from sklearn.neighbors import KNeighborsClassifier
model = KNeighborsClassifier(n_neighbors=3)
```

![](img/e364fa9e4347dee9913bb0c156837310_15.png)

---

![](img/e364fa9e4347dee9913bb0c156837310_17.png)

![](img/e364fa9e4347dee9913bb0c156837310_18.png)

## K最近邻算法如何工作？⚙️

![](img/e364fa9e4347dee9913bb0c156837310_20.png)

![](img/e364fa9e4347dee9913bb0c156837310_21.png)

上一节我们介绍了KNN的基本概念，本节中我们来看看它的具体工作步骤。

![](img/e364fa9e4347dee9913bb0c156837310_23.png)

![](img/e364fa9e4347dee9913bb0c156837310_24.png)

以下是K最近邻算法的基本步骤：

![](img/e364fa9e4347dee9913bb0c156837310_26.png)

1.  **加载带标签的数据**：这意味着数据的特征已知，并且我们有真实标签。
2.  **初始化K值**：K是一个整数，代表要考虑的邻居样本数量。
3.  **计算样本间距离**：可以使用欧几里得距离、曼哈顿距离或汉明距离。在本例中，我们使用欧几里得距离。其公式为：
    `distance = sqrt((x2 - x1)^2 + (y2 - y1)^2)`
4.  **对计算出的距离进行升序排序**。
5.  **从排序后的数组中选择前K行**。
6.  **分配类别**：根据这K个邻居中最常见的类别，为样本分配类别。

![](img/e364fa9e4347dee9913bb0c156837310_28.png)

---

![](img/e364fa9e4347dee9913bb0c156837310_30.png)

![](img/e364fa9e4347dee9913bb0c156837310_31.png)

![](img/e364fa9e4347dee9913bb0c156837310_32.png)

![](img/e364fa9e4347dee9913bb0c156837310_33.png)

## 何时使用K最近邻算法？📊

![](img/e364fa9e4347dee9913bb0c156837310_35.png)

![](img/e364fa9e4347dee9913bb0c156837310_36.png)

当给定一个带标签的数据集时，可以使用K最近邻算法，因为它是一种在带标签数据上运行的监督式机器学习算法。

如果我们有无标签数据，则无法使用K最近邻算法，因为它需要监督学习。

与其他算法相比，使用该算法的一个主要优势是它可以用于多类分类，这意味着我们可以识别多于一个类别。

如果你尝试对具有两个以上标签的数据进行分类，KNN可能是这种情况下最适合使用的算法。

![](img/e364fa9e4347dee9913bb0c156837310_38.png)

---

## 过拟合与欠拟合 ⚖️

现在，如果我们在模型中使用过多的邻居，则可能发生欠拟合。这意味着样本被认为不够重要，我们利用了过多的信息。

如果初始化和使用的邻居太少，则可能发生过拟合。这意味着每个样本都过于重要。

---

![](img/e364fa9e4347dee9913bb0c156837310_40.png)

## 实战演示：汽车价值评估 🚗

理论部分已经介绍完毕，现在让我们进入实战演示环节。我们将构建一个模型，根据汽车的某些属性来评估其价值。

首先，我们需要初始化所需的库并加载数据。

```python
import pandas as pd
import numpy as np
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn import preprocessing

# 加载数据
car_df = pd.read_csv('car.data')
```

请确保在上传并加载 `car.data` 文件。该数据集包含用于预测汽车价值的属性。

### 步骤一：数据预处理

![](img/e364fa9e4347dee9913bb0c156837310_42.png)

![](img/e364fa9e4347dee9913bb0c156837310_43.png)

![](img/e364fa9e4347dee9913bb0c156837310_44.png)

我们的数据集中有些属性是非数值型的，这不利于分类。因此，我们需要将它们转换为数值。

以下是数据预处理的步骤：

![](img/e364fa9e4347dee9913bb0c156837310_46.png)

![](img/e364fa9e4347dee9913bb0c156837310_47.png)

*   使用 `LabelEncoder` 将非数值标签转换为数值标签。
*   我们将使用的属性包括：购买价格、维护成本、车门数量、载客量、行李箱大小和安全性。
*   目标变量“class”代表汽车的价值等级（例如，0=低，1=中，2=高，3=很高）。

![](img/e364fa9e4347dee9913bb0c156837310_48.png)

![](img/e364fa9e4347dee9913bb0c156837310_49.png)

![](img/e364fa9e4347dee9913bb0c156837310_50.png)

![](img/e364fa9e4347dee9913bb0c156837310_51.png)

![](img/e364fa9e4347dee9913bb0c156837310_52.png)

```python
# 使用LabelEncoder转换特征
le = preprocessing.LabelEncoder()
buying = le.fit_transform(list(car_df["buying"]))
maint = le.fit_transform(list(car_df["maint"]))
door = le.fit_transform(list(car_df["door"]))
persons = le.fit_transform(list(car_df["persons"]))
lug_boot = le.fit_transform(list(car_df["lug_boot"]))
safety = le.fit_transform(list(car_df["safety"]))
cls = le.fit_transform(list(car_df["class"]))

![](img/e364fa9e4347dee9913bb0c156837310_54.png)

# 定义特征X和目标y
X = list(zip(buying, maint, door, persons, lug_boot, safety))
y = list(cls)
```

![](img/e364fa9e4347dee9913bb0c156837310_55.png)

![](img/e364fa9e4347dee9913bb0c156837310_56.png)

![](img/e364fa9e4347dee9913bb0c156837310_57.png)

### 步骤二：划分训练集和测试集

![](img/e364fa9e4347dee9913bb0c156837310_59.png)

![](img/e364fa9e4347dee9913bb0c156837310_60.png)

![](img/e364fa9e4347dee9913bb0c156837310_61.png)

接下来，我们需要将数据集划分为训练集和测试集。通常，我们使用70%的数据进行训练，30%的数据进行测试。

```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3)
```

![](img/e364fa9e4347dee9913bb0c156837310_63.png)

![](img/e364fa9e4347dee9913bb0c156837310_64.png)

![](img/e364fa9e4347dee9913bb0c156837310_65.png)

![](img/e364fa9e4347dee9913bb0c156837310_66.png)

![](img/e364fa9e4347dee9913bb0c156837310_67.png)

### 步骤三：创建KNN模型

现在，我们可以创建K最近邻分类器模型。这里我们将邻居数量 `n_neighbors` 设置为3。

![](img/e364fa9e4347dee9913bb0c156837310_69.png)

![](img/e364fa9e4347dee9913bb0c156837310_70.png)

![](img/e364fa9e4347dee9913bb0c156837310_71.png)

![](img/e364fa9e4347dee9913bb0c156837310_72.png)

```python
knn_model = KNeighborsClassifier(n_neighbors=3)
```

![](img/e364fa9e4347dee9913bb0c156837310_74.png)

![](img/e364fa9e4347dee9913bb0c156837310_75.png)

### 步骤四：训练模型

使用训练数据来训练我们的模型。

![](img/e364fa9e4347dee9913bb0c156837310_77.png)

![](img/e364fa9e4347dee9913bb0c156837310_78.png)

![](img/e364fa9e4347dee9913bb0c156837310_79.png)

![](img/e364fa9e4347dee9913bb0c156837310_80.png)

```python
knn_model.fit(X_train, y_train)
```

![](img/e364fa9e4347dee9913bb0c156837310_82.png)

### 步骤五：测试模型

![](img/e364fa9e4347dee9913bb0c156837310_83.png)

![](img/e364fa9e4347dee9913bb0c156837310_84.png)

![](img/e364fa9e4347dee9913bb0c156837310_85.png)

使用测试数据来评估模型的性能。

```python
predicted = knn_model.predict(X_test)
```

![](img/e364fa9e4347dee9913bb0c156837310_87.png)

![](img/e364fa9e4347dee9913bb0c156837310_88.png)

![](img/e364fa9e4347dee9913bb0c156837310_89.png)

![](img/e364fa9e4347dee9913bb0c156837310_90.png)

![](img/e364fa9e4347dee9913bb0c156837310_91.png)

### 步骤六：评估模型准确率

![](img/e364fa9e4347dee9913bb0c156837310_93.png)

![](img/e364fa9e4347dee9913bb0c156837310_94.png)

计算模型在测试集上的准确率。

```python
accuracy = knn_model.score(X_test, y_test)
print(f"模型准确率: {accuracy:.2%}")
# 输出示例：模型准确率: 85.93%
```

![](img/e364fa9e4347dee9913bb0c156837310_96.png)

![](img/e364fa9e4347dee9913bb0c156837310_97.png)

![](img/e364fa9e4347dee9913bb0c156837310_98.png)

![](img/e364fa9e4347dee9913bb0c156837310_99.png)

![](img/e364fa9e4347dee9913bb0c156837310_100.png)

### 步骤七：查看预测结果

最后，我们可以打印出预测结果，与真实值进行对比，以观察模型的性能。

![](img/e364fa9e4347dee9913bb0c156837310_102.png)

![](img/e364fa9e4347dee9913bb0c156837310_103.png)

![](img/e364fa9e4347dee9913bb0c156837310_104.png)

![](img/e364fa9e4347dee9913bb0c156837310_105.png)

```python
names = ["低", "中", "高", "很高"]
for x in range(len(predicted)):
    print(f"预测: {names[predicted[x]]}, 数据: {X_test[x]}, 实际: {names[y_test[x]]}")
```

通过调整超参数 `n_neighbors` 的值，你可以尝试获得更好的模型准确率。

---

![](img/e364fa9e4347dee9913bb0c156837310_107.png)

![](img/e364fa9e4347dee9913bb0c156837310_108.png)

![](img/e364fa9e4347dee9913bb0c156837310_109.png)

![](img/e364fa9e4347dee9913bb0c156837310_110.png)

![](img/e364fa9e4347dee9913bb0c156837310_111.png)

## 总结 📝

![](img/e364fa9e4347dee9913bb0c156837310_112.png)

![](img/e364fa9e4347dee9913bb0c156837310_113.png)

![](img/e364fa9e4347dee9913bb0c156837310_114.png)

![](img/e364fa9e4347dee9913bb0c156837310_116.png)

本节课中我们一起学习了K最近邻算法。我们了解了它是一种基于距离度量的监督学习算法，适用于分类和回归任务。我们探讨了其工作原理、如何选择K值以及过拟合与欠拟合的问题。最后，我们通过一个预测汽车价值的完整示例，实践了从数据预处理、模型构建、训练到评估的整个流程。记住，通过调整邻居数量K，可以优化模型的性能。