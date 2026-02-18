# 63：支持向量机原理 🧠

![](img/8c50ef80b9855d550ad96c543ec3e866_0.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_2.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_4.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_5.png)

在本节课中，我们将要学习支持向量机。这是一种监督式机器学习算法，特别适用于处理线性可分的数据。我们将了解它的工作原理、适用场景，并通过一个实战案例来掌握其应用。

![](img/8c50ef80b9855d550ad96c543ec3e866_7.png)

## 什么是支持向量机？🤔

![](img/8c50ef80b9855d550ad96c543ec3e866_9.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_10.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_11.png)

支持向量机是一种监督式机器学习算法，它最理想的应用场景是处理**线性可分**的数据，其工作原理与感知机类似。

![](img/8c50ef80b9855d550ad96c543ec3e866_12.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_13.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_14.png)

所谓线性可分，可以这样理解：我们有一条**超平面**（在二维空间中就是一条直线），这条线可以用来分隔不同类别的数据点。这些被分隔开的数据组可以被分类为特定的数据类型。支持向量机的核心就是插入一个超平面，将数据分割成不同的组。

## 支持向量机如何工作？⚙️

![](img/8c50ef80b9855d550ad96c543ec3e866_16.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_17.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_18.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_19.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_20.png)

我们的目标或任务是**最大化样本与决策边界之间的距离**。这意味着，我们有一个超平面，我们希望确保这个距离尽可能大，以使不同类别的数据点（例如图中的绿点和蓝点）能够被尽可能清晰地区分开。

![](img/8c50ef80b9855d550ad96c543ec3e866_22.png)

每个数据点被称为一个**支持向量**。

该算法的工作原理是创建一个超平面（即**决策边界**）来将数据分隔成不同的类别。决策边界决定了数据的分类方式：落在超平面一侧的数据被归为一个类别，而落在另一侧的数据则被归为另一个类别。

支持向量机算法优先寻找**最佳超平面**，即能够最大化分类间隔的那个超平面。

以下是在Python中创建支持向量机模型的一行核心代码：

```python
from sklearn.svm import SVC
model = SVC(kernel='linear')
```

我们指定核函数为`linear`，因为我们的数据是线性可分的。

## 何时使用支持向量机？📊

![](img/8c50ef80b9855d550ad96c543ec3e866_24.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_26.png)

由于它是一种监督式机器学习算法，我们通常在拥有**带标签的数据集**时使用它。

![](img/8c50ef80b9855d550ad96c543ec3e866_28.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_29.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_30.png)

在以下情况下，支持向量机比其他算法更有效：**数据集中特征的数量大于样本的数量**。这是使用该算法时需要记住的一个关键点。当特征多于数据样本，且数据已标记时，通常应使用支持向量机。

![](img/8c50ef80b9855d550ad96c543ec3e866_31.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_33.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_34.png)

当然，你可以尝试所有已学过的监督式机器学习算法，并通过比较执行后的性能（例如使用**准确率**作为指标）来确定哪种算法对你的数据效果最好。

![](img/8c50ef80b9855d550ad96c543ec3e866_36.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_38.png)

上一节我们介绍了支持向量机的基本概念和适用场景，本节中我们来看看如何通过一个具体的例子来应用它。

![](img/8c50ef80b9855d550ad96c543ec3e866_39.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_40.png)

## 实战演示：肿瘤分类 🩺

在本演示中，我们将使用支持向量机算法，根据肿瘤的特征将其分类为**恶性**或**良性**。

![](img/8c50ef80b9855d550ad96c543ec3e866_42.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_43.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_44.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_45.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_46.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_47.png)

### 第一步：加载库

![](img/8c50ef80b9855d550ad96c543ec3e866_48.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_49.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_50.png)

首先，我们需要导入必要的Python库。

![](img/8c50ef80b9855d550ad96c543ec3e866_52.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_54.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_55.png)

```python
from sklearn import datasets
from sklearn import svm
from sklearn.metrics import accuracy_score
from sklearn.model_selection import train_test_split
```

![](img/8c50ef80b9855d550ad96c543ec3e866_56.png)

### 第二步：加载与理解数据

![](img/8c50ef80b9855d550ad96c543ec3e866_58.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_59.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_60.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_61.png)

我们将使用Scikit-learn内置的乳腺癌数据集。该数据集包含许多特征，例如肿瘤的平均半径、纹理、周长、面积、平滑度等。目标类别是“恶性”（0）或“良性”（1）。

![](img/8c50ef80b9855d550ad96c543ec3e866_63.png)

以下是加载数据的代码：

![](img/8c50ef80b9855d550ad96c543ec3e866_65.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_66.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_67.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_68.png)

```python
cancer_data = datasets.load_breast_cancer()
```

![](img/8c50ef80b9855d550ad96c543ec3e866_69.png)

你可以打印出`cancer_data.feature_names`和`cancer_data.target_names`来查看所有特征和类别名称。

### 第三步：准备数据

![](img/8c50ef80b9855d550ad96c543ec3e866_71.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_72.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_73.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_74.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_75.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_76.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_77.png)

接下来，我们将特征数据与目标标签分开，并将数据集划分为训练集和测试集。

![](img/8c50ef80b9855d550ad96c543ec3e866_79.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_80.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_81.png)

```python
X = cancer_data.data  # 特征
y = cancer_data.target  # 目标标签

![](img/8c50ef80b9855d550ad96c543ec3e866_83.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_85.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_86.png)

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```

我们将70%的数据用于训练，30%用于测试。

![](img/8c50ef80b9855d550ad96c543ec3e866_88.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_89.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_90.png)

### 第四步：创建与训练模型

![](img/8c50ef80b9855d550ad96c543ec3e866_91.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_92.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_93.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_95.png)

现在，我们创建支持向量机分类器模型并对其进行训练。

![](img/8c50ef80b9855d550ad96c543ec3e866_96.png)

```python
svm_model = svm.SVC(kernel='linear')  # 创建模型，指定线性核
svm_model.fit(X_train, y_train)       # 训练模型
```

![](img/8c50ef80b9855d550ad96c543ec3e866_98.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_99.png)

### 第五步：进行预测与评估

![](img/8c50ef80b9855d550ad96c543ec3e866_101.png)

使用训练好的模型对测试集进行预测，并计算模型的准确率。

![](img/8c50ef80b9855d550ad96c543ec3e866_102.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_103.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_104.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_105.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_106.png)

```python
y_pred = svm_model.predict(X_test)  # 预测

![](img/8c50ef80b9855d550ad96c543ec3e866_108.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_109.png)

accuracy = accuracy_score(y_test, y_pred)  # 计算准确率
print(f"模型准确率: {accuracy:.2%}")
```

![](img/8c50ef80b9855d550ad96c543ec3e866_110.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_112.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_113.png)

运行上述脚本后，我们得到了约96.49%的准确率，这表明我们的线性核函数在这个线性可分数据集上表现良好。

![](img/8c50ef80b9855d550ad96c543ec3e866_114.png)

### 第六步：分析结果

![](img/8c50ef80b9855d550ad96c543ec3e866_116.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_117.png)

我们可以通过一个循环来查看部分预测结果与实际值的对比：

![](img/8c50ef80b9855d550ad96c543ec3e866_118.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_119.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_120.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_121.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_122.png)

```python
for i in range(10):
    print(f"样本 {i}: 预测 = {y_pred[i]}, 实际 = {y_test[i]}")
```

![](img/8c50ef80b9855d550ad96c543ec3e866_124.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_125.png)

输出会显示，大多数预测是正确的，但也存在少数预测错误的情况（例如预测为良性但实际是恶性），这对应了那约4%的错误率。

![](img/8c50ef80b9855d550ad96c543ec3e866_126.png)

## 总结与优化 🎯

![](img/8c50ef80b9855d550ad96c543ec3e866_128.png)

本节课中我们一起学习了支持向量机。我们了解到它是一种用于线性可分数据的强大分类器，其核心思想是寻找最大化间隔的超平面。通过乳腺癌分类的实战，我们掌握了使用Scikit-learn库构建、训练和评估SVM模型的完整流程。

![](img/8c50ef80b9855d550ad96c543ec3e866_129.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_130.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_131.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_132.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_133.png)

模型的性能（96.49%的准确率）已经很好，但并非完美。为了获得更优的预测性能，我们可以：
*   **调整超参数**：尝试不同的核函数（如`rbf`、`poly`）或调整其他参数（如`C`值）。
*   **进一步清理和预处理数据**：确保输入模型的数据质量更高。

![](img/8c50ef80b9855d550ad96c543ec3e866_135.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_137.png)

![](img/8c50ef80b9855d550ad96c543ec3e866_138.png)

通过不断迭代和优化，我们可以使模型达到更好的状态。