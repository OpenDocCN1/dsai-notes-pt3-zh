# 37：📊 Python中使用Matplotlib库进行数据可视化

![](img/fad61f97b3873030b4ecc4e46949214e_0.png)

![](img/fad61f97b3873030b4ecc4e46949214e_2.png)

![](img/fad61f97b3873030b4ecc4e46949214e_4.png)

在本节课中，我们将要学习Python中一个强大的数据可视化库——Matplotlib。我们将了解Matplotlib是什么，并探索如何使用它来创建多种类型的图表，包括折线图、条形图、散点图、箱线图和直方图。

![](img/fad61f97b3873030b4ecc4e46949214e_6.png)

![](img/fad61f97b3873030b4ecc4e46949214e_7.png)

![](img/fad61f97b3873030b4ecc4e46949214e_8.png)

![](img/fad61f97b3873030b4ecc4e46949214e_9.png)

## 什么是Matplotlib？🤔

![](img/fad61f97b3873030b4ecc4e46949214e_11.png)

![](img/fad61f97b3873030b4ecc4e46949214e_13.png)

![](img/fad61f97b3873030b4ecc4e46949214e_14.png)

Matplotlib是一个用于在Python中创建静态、动画或交互式可视化的综合库。它极大地简化了数据可视化的过程，使得在Python中实现以前难以完成的任务成为可能。

![](img/fad61f97b3873030b4ecc4e46949214e_16.png)

## 创建折线图 📈

![](img/fad61f97b3873030b4ecc4e46949214e_18.png)

![](img/fad61f97b3873030b4ecc4e46949214e_19.png)

![](img/fad61f97b3873030b4ecc4e46949214e_21.png)

上一节我们介绍了Matplotlib的基本概念，本节中我们来看看如何创建最基础的图表类型——折线图。折线图通常用于展示趋势、比较多个值、观察数值随时间的变化、分析数值数据以及进行预测。

![](img/fad61f97b3873030b4ecc4e46949214e_23.png)

![](img/fad61f97b3873030b4ecc4e46949214e_24.png)

![](img/fad61f97b3873030b4ecc4e46949214e_25.png)

以下是创建折线图的基本步骤：

![](img/fad61f97b3873030b4ecc4e46949214e_27.png)

![](img/fad61f97b3873030b4ecc4e46949214e_29.png)

![](img/fad61f97b3873030b4ecc4e46949214e_31.png)

1.  **导入库**：首先需要导入Matplotlib的`pyplot`模块，通常别名为`plt`。
    ```python
    import matplotlib.pyplot as plt
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_33.png)

![](img/fad61f97b3873030b4ecc4e46949214e_35.png)

![](img/fad61f97b3873030b4ecc4e46949214e_37.png)

2.  **准备数据**：定义X轴和Y轴的数据。
    ```python
    x = range(10)
    y = [i**2 for i in x]  # 示例：y = x^2
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_39.png)

![](img/fad61f97b3873030b4ecc4e46949214e_41.png)

3.  **绘制图形**：使用`plt.plot()`函数绘制折线。
    ```python
    plt.plot(x, y)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_43.png)

![](img/fad61f97b3873030b4ecc4e46949214e_44.png)

![](img/fad61f97b3873030b4ecc4e46949214e_46.png)

4.  **添加标签和标题**：为图表和坐标轴添加说明。
    ```python
    plt.xlabel(‘X轴标签’)
    plt.ylabel(‘Y轴标签’)
    plt.title(‘图表标题’)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_48.png)

![](img/fad61f97b3873030b4ecc4e46949214e_50.png)

![](img/fad61f97b3873030b4ecc4e46949214e_51.png)

5.  **设置坐标轴范围**：可以手动设置X轴和Y轴的显示范围。
    ```python
    plt.ylim(-2000, 2000)  # 设置Y轴范围
    # plt.xlim() 用于设置X轴范围
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_53.png)

![](img/fad61f97b3873030b4ecc4e46949214e_54.png)

6.  **添加参考线**：可以添加水平或垂直的参考线。
    ```python
    plt.axhline(y=0, color=‘black’)  # 在y=0处添加水平线
    plt.axvline(x=0, color=‘black’)  # 在x=0处添加垂直线
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_56.png)

![](img/fad61f97b3873030b4ecc4e46949214e_58.png)

7.  **保存图表**：将图表保存为图片文件。
    ```python
    plt.savefig(‘my_plot.png’)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_60.png)

![](img/fad61f97b3873030b4ecc4e46949214e_62.png)

![](img/fad61f97b3873030b4ecc4e46949214e_64.png)

8.  **显示图表**：最后，必须使用`plt.show()`来显示图表。
    ```python
    plt.show()
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_66.png)

![](img/fad61f97b3873030b4ecc4e46949214e_68.png)

## 自定义折线图样式 🎨

![](img/fad61f97b3873030b4ecc4e46949214e_70.png)

![](img/fad61f97b3873030b4ecc4e46949214e_72.png)

除了基本绘图，我们还可以自定义折线的样式，使其更具表现力。

![](img/fad61f97b3873030b4ecc4e46949214e_74.png)

以下是自定义折线样式的关键参数：

*   **线型 (`linestyle`)**：使用`‘-‘`表示实线，`‘–‘`表示虚线，`‘:‘`表示点线，`‘-.’`表示点划线。
*   **线宽 (`linewidth`)**：设置线条的粗细。
*   **颜色 (`color`)**：设置线条的颜色，可以使用颜色名称（如`‘purple’`）或十六进制值。
*   **标记 (`marker`)**：在数据点上添加标记，如`‘o’`（圆圈）、`‘s’`（方块）、`‘^’`（三角形）。
*   **图例 (`legend`)**：使用`plt.legend()`显示图例，用于区分多条线。

示例代码：
```python
plt.plot(x, y, linestyle=‘–’, linewidth=2, color=‘purple’, marker=‘o’, label=‘数据系列1’)
plt.legend()
```

![](img/fad61f97b3873030b4ecc4e46949214e_76.png)

## 创建条形图 📊

![](img/fad61f97b3873030b4ecc4e46949214e_78.png)

![](img/fad61f97b3873030b4ecc4e46949214e_80.png)

接下来，我们看看如何创建条形图。条形图非常适合比较不同类别的数据，特别是当你有三个或更多需要比较的元素时。

![](img/fad61f97b3873030b4ecc4e46949214e_81.png)

![](img/fad61f97b3873030b4ecc4e46949214e_83.png)

以下是创建分组条形图的步骤：

![](img/fad61f97b3873030b4ecc4e46949214e_84.png)

![](img/fad61f97b3873030b4ecc4e46949214e_86.png)

![](img/fad61f97b3873030b4ecc4e46949214e_87.png)

1.  **导入库并准备数据**：除了Matplotlib，通常还会用到NumPy来辅助定位。
    ```python
    import matplotlib.pyplot as plt
    import numpy as np

    companies = [‘Google‘, ‘Amazon‘, ‘Microsoft‘, ‘Facebook‘]
    revenue = [90, 136, 89, 27]  # 单位：十亿美元
    profit = [20, 22, 30, 10]   # 示例利润数据
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_89.png)

![](img/fad61f97b3873030b4ecc4e46949214e_91.png)

![](img/fad61f97b3873030b4ecc4e46949214e_92.png)

2.  **设置条形位置**：使用`np.arange()`生成条形组的索引位置。
    ```python
    x_indexes = np.arange(len(companies))
    width = 0.35  # 每个条形的宽度
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_94.png)

![](img/fad61f97b3873030b4ecc4e46949214e_96.png)

3.  **绘制条形**：使用`plt.bar()`绘制条形。通过调整`x`参数的位置可以绘制并排的分组条形。
    ```python
    plt.bar(x_indexes - width/2, revenue, width=width, label=‘营收‘)
    plt.bar(x_indexes + width/2, profit, width=width, label=‘利润‘)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_98.png)

4.  **设置X轴刻度标签**：将数字位置替换为公司名称。
    ```python
    plt.xticks(ticks=x_indexes, labels=companies)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_100.png)

![](img/fad61f97b3873030b4ecc4e46949214e_101.png)

![](img/fad61f97b3873030b4ecc4e46949214e_102.png)

![](img/fad61f97b3873030b4ecc4e46949214e_104.png)

5.  **添加标签、标题和图例**：
    ```python
    plt.xlabel(‘公司‘)
    plt.ylabel(‘金额 (十亿美元)‘)
    plt.title(‘科技公司营收与利润对比‘)
    plt.legend()
    plt.show()
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_106.png)

![](img/fad61f97b3873030b4ecc4e46949214e_108.png)

![](img/fad61f97b3873030b4ecc4e46949214e_110.png)

## 创建散点图 ✨

![](img/fad61f97b3873030b4ecc4e46949214e_112.png)

![](img/fad61f97b3873030b4ecc4e46949214e_114.png)

现在，我们来学习散点图。散点图主要用于可视化两个变量集之间的关系，是识别大数据集中相关性、预测行为和衡量独立值的绝佳方式。

![](img/fad61f97b3873030b4ecc4e46949214e_115.png)

创建散点图非常简单：

![](img/fad61f97b3873030b4ecc4e46949214e_117.png)

![](img/fad61f97b3873030b4ecc4e46949214e_118.png)

![](img/fad61f97b3873030b4ecc4e46949214e_120.png)

![](img/fad61f97b3873030b4ecc4e46949214e_122.png)

1.  **准备数据**：定义两组相关的数据。
    ```python
    x = [1, 2, 3, 4, 5]
    y = [2, 4, 6, 8, 10]
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_124.png)

![](img/fad61f97b3873030b4ecc4e46949214e_126.png)

2.  **绘制散点**：使用`plt.scatter()`函数。
    ```python
    plt.scatter(x, y, label=‘散点数据‘, marker=‘x‘) # marker可设置为’o‘, ’s‘, ’^‘等
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_128.png)

![](img/fad61f97b3873030b4ecc4e46949214e_129.png)

3.  **添加装饰**：
    ```python
    plt.xlabel(‘X值‘)
    plt.ylabel(‘Y值‘)
    plt.title(‘散点图示例‘)
    plt.legend()
    plt.show()
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_131.png)

![](img/fad61f97b3873030b4ecc4e46949214e_133.png)

## 创建箱线图 📦

![](img/fad61f97b3873030b4ecc4e46949214e_135.png)

![](img/fad61f97b3873030b4ecc4e46949214e_136.png)

![](img/fad61f97b3873030b4ecc4e46949214e_137.png)

箱线图（又称盒须图）用于统计图形和数值数据的展示，可以很好地显示数据的范围、分布和中心趋势。

![](img/fad61f97b3873030b4ecc4e46949214e_139.png)

![](img/fad61f97b3873030b4ecc4e46949214e_141.png)

创建箱线图可能需要结合Pandas、NumPy和Seaborn等库（这里以Seaborn为例，它是基于Matplotlib的高级统计绘图库）：

![](img/fad61f97b3873030b4ecc4e46949214e_143.png)

![](img/fad61f97b3873030b4ecc4e46949214e_145.png)

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

![](img/fad61f97b3873030b4ecc4e46949214e_147.png)

![](img/fad61f97b3873030b4ecc4e46949214e_148.png)

![](img/fad61f97b3873030b4ecc4e46949214e_150.png)

# 1. 读取数据
data = pd.read_csv(‘data.csv‘)

![](img/fad61f97b3873030b4ecc4e46949214e_152.png)

![](img/fad61f97b3873030b4ecc4e46949214e_154.png)

# 2. 使用Seaborn创建箱线图
sns.boxplot(x=‘category_column‘, y=‘value_column‘, data=data)

![](img/fad61f97b3873030b4ecc4e46949214e_156.png)

![](img/fad61f97b3873030b4ecc4e46949214e_158.png)

# 3. 使用Matplotlib进行装饰
plt.title(‘箱线图标题‘)
plt.xlabel(‘X轴标签‘)
plt.ylabel(‘Y轴标签‘)
plt.show()
```

![](img/fad61f97b3873030b4ecc4e46949214e_159.png)

![](img/fad61f97b3873030b4ecc4e46949214e_160.png)

![](img/fad61f97b3873030b4ecc4e46949214e_162.png)

## 创建直方图 📋

![](img/fad61f97b3873030b4ecc4e46949214e_164.png)

![](img/fad61f97b3873030b4ecc4e46949214e_165.png)

最后，我们学习直方图。直方图用于展示连续数据的频率分布，可以总结大型数据集，并比较不同的分布。

![](img/fad61f97b3873030b4ecc4e46949214e_167.png)

![](img/fad61f97b3873030b4ecc4e46949214e_169.png)

以下是创建直方图的步骤：

![](img/fad61f97b3873030b4ecc4e46949214e_171.png)

![](img/fad61f97b3873030b4ecc4e46949214e_173.png)

1.  **准备数据**：通常是一组连续值，如年龄。
    ```python
    import matplotlib.pyplot as plt
    import pandas as pd

    data = pd.read_csv(‘ages.csv‘)
    ages = data[‘Age‘]
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_175.png)

![](img/fad61f97b3873030b4ecc4e46949214e_176.png)

![](img/fad61f97b3873030b4ecc4e46949214e_178.png)

2.  **设置分组区间**：定义直方图的柱子范围。
    ```python
    bins = range(0, 81, 10)  # 从0到80，每10岁一组
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_180.png)

![](img/fad61f97b3873030b4ecc4e46949214e_182.png)

![](img/fad61f97b3873030b4ecc4e46949214e_184.png)

3.  **绘制直方图**：使用`plt.hist()`。
    ```python
    plt.hist(ages, bins=bins, edgecolor=‘black‘)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_186.png)

![](img/fad61f97b3873030b4ecc4e46949214e_187.png)

4.  **添加平均线（可选）**：计算平均值并添加一条垂直线。
    ```python
    mean_age = ages.mean()
    plt.axvline(mean_age, color=‘red‘, linestyle=‘dashed‘, linewidth=2, label=f‘平均年龄：{mean_age:.1f}‘)
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_189.png)

![](img/fad61f97b3873030b4ecc4e46949214e_191.png)

![](img/fad61f97b3873030b4ecc4e46949214e_193.png)

5.  **添加装饰**：
    ```python
    plt.xlabel(‘年龄‘)
    plt.ylabel(‘人数‘)
    plt.title(‘年龄分布直方图‘)
    plt.legend()
    plt.show()
    ```

![](img/fad61f97b3873030b4ecc4e46949214e_195.png)

![](img/fad61f97b3873030b4ecc4e46949214e_197.png)

## 总结 🎯

![](img/fad61f97b3873030b4ecc4e46949214e_198.png)

![](img/fad61f97b3873030b4ecc4e46949214e_200.png)

![](img/fad61f97b3873030b4ecc4e46949214e_202.png)

本节课中我们一起学习了Python数据可视化的核心工具Matplotlib。我们从了解Matplotlib是什么开始，逐步掌握了如何创建和自定义**折线图**、**条形图**、**散点图**、**箱线图**和**直方图**。记住，无论创建哪种图表，基本的流程都包括：导入库、准备数据、调用对应的绘图函数（如`plot`， `bar`， `scatter`）、添加坐标轴标签和标题，最后使用`plt.show()`显示图表。通过灵活运用样式参数，你可以创建出既美观又信息丰富的可视化图形。