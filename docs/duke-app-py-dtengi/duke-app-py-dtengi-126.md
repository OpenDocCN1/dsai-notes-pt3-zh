#  126：使用Seaborn创建热力图

![](img/f7afac6d557899d6b563fabf5d13eb7c_0.png)

在本节课中，我们将学习如何使用Seaborn库快速创建热力图。热力图是一种非常直观的数据可视化方式，能够清晰地展示数据矩阵中数值的分布和大小关系。我们将通过一个具体的例子，演示从加载数据到生成并美化热力图的完整过程。

## 加载数据

首先，我们需要加载将要使用的数据。在这个例子中，我们将使用一份总统相关的数据集。

```python
# 假设presidential_data是已经加载好的Pandas DataFrame
import pandas as pd
# 加载数据的代码（此处为示意，具体加载方式取决于数据源）
# presidential_data = pd.read_csv('your_data.csv')
```

## 创建基础热力图

上一节我们加载了数据，本节中我们来看看如何使用Seaborn创建基础热力图。Seaborn库内置了`sns.heatmap`函数，这使得创建热力图变得非常简单，而无需依赖Pandas或Matplotlib的复杂操作。

以下是创建基础热力图的代码：

```python
import seaborn as sns
import matplotlib.pyplot as plt

# 一行代码创建热力图
sns.heatmap(presidential_data)
plt.show()
```

执行上述代码后，将生成一个基础的热力图。需要记住的是，`sns.heatmap`函数的返回值是一个Matplotlib的`AxesSubplot`对象，这意味着我们可以像操作其他Matplotlib图表一样，对它进行各种自定义和美化。

## 美化热力图

基础热力图已经能够展示数据，但我们通常希望它更具可读性和美观性。接下来，我们将对图表进行一系列美化操作。

以下是美化热力图的具体步骤列表：

1.  **更改配色方案**：使用`cmap`参数将颜色映射改为“RdBu_r”，这是一种红蓝反向的配色，能提供更好的对比。
2.  **添加数值标注**：设置`annot=True`，在热力图的每个单元格中显示具体的数值。
3.  **设置颜色条标签**：通过`cbar_kws`参数为颜色条添加一个描述性标签。
4.  **调整坐标轴标签**：清除Y轴标签，并为图表设置一个标题。

让我们将这些步骤应用到代码中：

```python
# 创建并美化热力图
ax = sns.heatmap(presidential_data,
                 cmap='RdBu_r',      # 使用红蓝反向配色
                 annot=True,         # 在单元格中显示数值
                 cbar_kws={'label': '数值范围'}  # 设置颜色条标签
                )

# 进一步的美化
ax.set_ylabel('')  # 清除Y轴标签
ax.set_title('总统数据热力图分析')  # 设置图表标题

plt.show()
```

经过美化后，我们得到了一张信息更丰富、视觉效果更好的热力图。虽然这个例子没有使用黑色背景等特定样式，但通过寥寥数行代码，我们已经能够生成一个非常实用且专业的图表。

## 总结

![](img/f7afac6d557899d6b563fabf5d13eb7c_2.png)

本节课中我们一起学习了如何使用Seaborn库创建和美化热力图。我们首先加载了数据，然后使用`sns.heatmap`函数快速生成了基础图表。最后，我们通过调整配色、添加数值标注和设置标签等步骤，显著提升了图表的可读性和专业性。掌握Seaborn的热力图功能，能让你在数据探索和展示时事半功倍。