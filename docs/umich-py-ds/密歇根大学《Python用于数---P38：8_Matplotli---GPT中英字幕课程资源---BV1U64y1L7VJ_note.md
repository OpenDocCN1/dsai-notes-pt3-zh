# 课程1-3：Python数据科学实践 🐍
## 第8讲：Matplotlib入门 📊

在本节课中，我们将学习如何使用Python的Matplotlib工具包创建基本图表。我们将从了解Matplotlib的架构开始，然后逐步学习如何绘制散点图、折线图和条形图。

---

欢迎来到本课程的第二模块：“Python中的应用绘图、图表与数据表示”。

![](img/20e9c9592ee8969d5c5a49c2ef1ed4b0_0.png)

在第一模块中，我们借鉴了该领域有影响力的思想家（如Alberto Cairo和Edward Tufte）的观点，探讨了构建优质信息图表的一些基本原理。

在本模块中，我们将转向重点，学习使用基于Python的Matplotlib工具包构建基本图表的技能。

Matplotlib是一个用于表示和可视化数据的强大开源工具包。其创建者John Hunter深受Matlab编程环境的启发，并借鉴了其中的许多元素。

然而，从网络资源学习Matplotlib可能会有些令人困惑。它有一个传统的面向对象API，但也有一个类似Matlab的脚本模型。我发现，有时并不清楚为什么博客文章中的某个特定脚本能运行或不能运行。

我将尝试通过提供对该工具的结构化介绍，为您揭开一些神秘面纱。

在架构介绍之后，我们将直接深入创建图表。

在本模块中，我们将重点介绍一些基础知识：散点图、折线图和条形图。我们还将探讨如何为图表的各个部分添加标签以提高可读性，如何引导用户关注特定细节，以及如何在绘图环境中操作数据元素。

从现在开始，讲座内容会减少，模块的重点将更多地放在绘图和图表作业上。

在模块2、3和4结束时，您应该能够使用广泛的数据制作出具有出版质量的图表和图形。

让我们开始吧。

---

### Matplotlib架构简介 🏗️

上一节我们概述了本模块的目标，本节中我们来看看Matplotlib的基本架构。理解其设计有助于更有效地使用它。

Matplotlib的核心是一个分层系统。最底层是**后端（Backend）**，它负责在不同的输出设备（如屏幕或文件）上实际渲染图形。中间层是**艺术家（Artist）**层，它处理所有高级绘图元素，如坐标轴、线条和文本。最顶层是**脚本（Scripting）**层，即`pyplot`接口，它提供了类似MATLAB的快速绘图命令。

以下是两种主要的使用方式：

**1. 面向对象接口（推荐）**
这种方式显式地创建图形（Figure）和坐标轴（Axes）对象，然后在这些对象上调用方法。它更清晰、更灵活，适合复杂的图表。

```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots()  # 创建图形和坐标轴对象
ax.plot([1, 2, 3, 4], [1, 4, 2, 3])  # 在坐标轴对象上绘图
plt.show()
```

**2. Pyplot脚本接口**
这种方式使用`plt`模块下的函数（如`plt.plot()`）隐式地操作“当前图形”和“当前坐标轴”。它更简单快捷，适合交互式环境和简单脚本。

```python
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [1, 4, 2, 3])  # pyplot隐式管理图形和坐标轴
plt.show()
```

初学者常感到困惑的原因是混合使用了这两种风格。本教程将主要使用**面向对象接口**，因为它概念更清晰，代码更易维护。

---

### 创建基本图表 📈

了解了架构之后，我们现在可以开始动手创建图表了。本节将介绍三种最基础的图表类型。

以下是创建任何图表的基本步骤框架：

1.  导入库：`import matplotlib.pyplot as plt`
2.  准备数据。
3.  创建图形和坐标轴：`fig, ax = plt.subplots()`
4.  在坐标轴`ax`上调用绘图方法（如`ax.plot()`）。
5.  自定义图表（添加标题、标签等）。
6.  显示或保存图表：`plt.show()` 或 `fig.savefig()`。

#### 散点图

散点图用于展示两个连续变量之间的关系，观察数据的分布或聚类情况。

```python
import matplotlib.pyplot as plt
import numpy as np

# 生成示例数据
x = np.random.rand(50)
y = np.random.rand(50)

fig, ax = plt.subplots()
ax.scatter(x, y)  # 创建散点图
ax.set_title('随机散点图')
ax.set_xlabel('X轴')
ax.set_ylabel('Y轴')
plt.show()
```

#### 折线图

折线图通常用于显示数据随时间或有序类别的变化趋势。

```python
# 继续使用上面的fig, ax
years = [2010, 2012, 2014, 2016, 2018, 2020]
sales = [100, 120, 90, 150, 200, 180]

ax.clear()  # 清除之前的图形
ax.plot(years, sales, marker='o')  # 创建折线图，'o'表示数据点标记
ax.set_title('年度销售额趋势')
ax.set_xlabel('年份')
ax.set_ylabel('销售额（万）')
plt.show()
```

#### 条形图

条形图适用于比较不同类别之间的离散数据。

```python
categories = ['产品A', '产品B', '产品C', '产品D']
values = [23, 45, 56, 78]

fig, ax = plt.subplots()
ax.bar(categories, values)  # 创建垂直条形图
# ax.barh(categories, values) # 创建水平条形图
ax.set_title('产品销量对比')
ax.set_ylabel('销量')
plt.show()
```

---

### 增强图表可读性 🎨

仅仅画出图形还不够，专业的图表需要清晰的标注和适度的美化来引导读者。本节我们来看看如何实现这一点。

以下是为图表添加常见标注和美化的方法：

*   **添加标题和轴标签**：使用`ax.set_title()`、`ax.set_xlabel()`、`ax.set_ylabel()`。
*   **添加图例**：在绘图时指定`label`参数，然后调用`ax.legend()`。
*   **设置坐标轴范围**：使用`ax.set_xlim([xmin, xmax])`和`ax.set_ylim([ymin, ymax])`。
*   **添加网格**：使用`ax.grid(True)`。
*   **自定义颜色和样式**：在绘图函数中使用`color`、`linestyle`、`linewidth`等参数。

```python
# 综合示例
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

fig, ax = plt.subplots(figsize=(8, 5))  # 设置图形大小

# 绘制两条线，并指定标签
ax.plot(x, y1, label='sin(x)', color='blue', linewidth=2)
ax.plot(x, y2, label='cos(x)', color='red', linestyle='--')

# 添加标注
ax.set_title('正弦与余弦函数曲线', fontsize=14)
ax.set_xlabel('X轴', fontsize=12)
ax.set_ylabel('Y轴', fontsize=12)
ax.legend()
ax.grid(True, linestyle=':', alpha=0.6)  # 添加半透明虚线网格

plt.show()
```

---

### 总结 🎯

本节课中我们一起学习了Matplotlib的基础知识。我们首先介绍了Matplotlib的分层架构，并对比了面向对象和Pyplot脚本两种编程接口，推荐使用更清晰的面向对象方式。

接着，我们实践了三种基本图表的创建：观察关系的**散点图**、展示趋势的**折线图**以及进行比较的**条形图**。最后，我们学习了如何通过添加标题、标签、图例和网格等元素来显著增强图表的可读性和专业性。

掌握这些基础是迈向制作出版质量图表的第一步。在接下来的练习和模块中，你将有机会应用这些技能处理更复杂的数据和图表类型。