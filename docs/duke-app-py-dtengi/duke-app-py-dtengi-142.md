#  142：Streamlit简介 🚀

在本节中，我们将学习Streamlit。Streamlit是另一个用于在Python中创建仪表板的库。

## 概述

上一节我们介绍了使用Plotly创建交互式图表。本节中，我们来看看如何利用Streamlit库，将这些图表整合到一个功能完整的Web应用仪表板中。Streamlit简化了数据应用的构建过程，让开发者能够快速将数据脚本转化为可共享的Web应用。

## 什么是Streamlit？

Streamlit是一个开源的Python库，它允许数据科学家和工程师快速构建和分享美观、交互式的数据应用。你无需学习前端技术（如HTML、CSS、JavaScript），只需使用纯Python代码即可创建应用。

其核心思想是**将脚本视为应用**。每当你保存脚本，Streamlit应用就会自动更新，这极大地提高了开发效率。

## 核心概念与工作方式

Streamlit应用围绕一个脚本运行。当你运行`streamlit run your_script.py`命令时，会发生以下事情：

1.  Streamlit从头到尾执行你的脚本。
2.  脚本中调用的Streamlit函数（如`st.write`， `st.dataframe`）会向应用的前端界面发送指令。
3.  每次与前端的小部件（如下拉菜单、滑块）交互时，Streamlit都会从头到尾重新执行整个脚本。

这种执行模型简单直观，但要求代码能够高效执行。对于耗时的计算，可以使用`@st.cache_data`装饰器进行缓存。

```python
import streamlit as st

@st.cache_data
def load_large_dataset():
    # 这里执行耗时的数据加载操作
    data = ...
    return data

data = load_large_dataset()
st.write(data)
```

## 基本组件与用法

以下是构建Streamlit应用时最常用的一些组件。

![](img/4516cb6599fdb0576351b9cef76b1850_0.png)

### 显示文本与数据

使用`st.write()`可以显示几乎任何内容：文本、数据、图表。它是Streamlit中最通用的命令。

```python
st.write("Hello, Streamlit!")
st.write(df) # 显示一个Pandas DataFrame
```

### 添加标题与标题

`st.title()`和`st.header()`用于组织应用的布局结构。

```python
st.title("我的数据分析仪表板")
st.header("第一章：销售数据概览")
```

### 创建交互式小部件

小部件允许用户与应用交互。以下是一些常用的小部件示例。

```python
# 按钮
if st.button("点击我"):
    st.write("按钮被点击了！")

# 复选框
show_data = st.checkbox("显示原始数据")
if show_data:
    st.write(df)

# 下拉选择框
option = st.selectbox(
    "请选择一个选项：",
    ["选项A", "选项B", "选项C"]
)
st.write("你选择了：", option)

# 滑块
age = st.slider("请选择你的年龄：", 0, 100, 25)
st.write("你的年龄是：", age)
```

### 布局与容器

为了创建更复杂的布局，Streamlit提供了列和容器。

```python
# 创建两列
col1, col2 = st.columns(2)

with col1:
    st.header("列1")
    st.line_chart([1, 2, 3, 4])

with col2:
    st.header("列2")
    st.area_chart([1, 2, 3, 4])
```

### 显示图表

Streamlit原生支持多种图表库，如Matplotlib、Plotly、Altair等。

```python
import matplotlib.pyplot as plt
import numpy as np

# 使用Matplotlib
fig, ax = plt.subplots()
x = np.linspace(0, 10, 100)
ax.plot(x, np.sin(x))
st.pyplot(fig)

# 使用Streamlit原生图表（基于Altair）
st.line_chart(df[['column_a', 'column_b']])
```

## 总结

本节课中我们一起学习了Streamlit的基础知识。我们了解到Streamlit是一个强大的Python库，能够将数据脚本快速转变为交互式Web应用。我们介绍了其核心执行模型、常用组件如文本显示、交互式小部件、布局管理以及图表集成。掌握这些基础后，你就可以开始构建自己的数据仪表板，将数据分析结果生动地呈现给他人。在接下来的课程中，我们将结合具体案例，实践如何用Streamlit构建一个完整的数据工程应用。