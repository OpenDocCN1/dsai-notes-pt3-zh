**Python数据可视化：第3课：使用Seaborn创建折线图** 🎨

![](img/5303c60389925e7ee8eefeedddd3a563_0.png)

在本节课中，我们将学习如何使用Seaborn库快速创建折线图。我们将重现一个关于支出的折线图，并了解Seaborn如何简化数据分组和可视化过程。

---

首先，我们需要加载数据。

```python
# 假设数据已加载到名为 `df` 的DataFrame中
```

接下来，我们使用一行代码创建基础的折线图。

```python
import seaborn as sns
sns.lineplot(data=df, x='Year', y='Spending', hue='Country')
```

通过这行代码，我们得到了一个基本的折线图。Seaborn的强大之处在于，它允许我们通过指定 `hue` 参数（例如按“国家”分类）来拆分数据，而无需手动进行分组操作。

如果我们设置 `sort=False`，折线将不会自动排序，从而可能产生回折的线条。

```python
sns.lineplot(data=df, x='Year', y='Spending', hue='Country', sort=False)
```

现在，让我们尝试清理图表并使其看起来更美观。

以下是优化后的代码示例：

```python
# 筛选特定国家并指定顺序
countries_to_plot = ['USA', 'UK', 'Germany']
palette_dict = {'USA': 'red', 'UK': 'blue', 'Germany': 'green'}

# 创建图表
ax = sns.lineplot(
    data=df[df['Country'].isin(countries_to_plot)],
    x='Year',
    y='Spending',
    hue='Country',
    hue_order=countries_to_plot,
    palette=palette_dict,
    sort=False
)

# 设置标题和Y轴范围
ax.set_title('Annual Spending by Country')
ax.set_ylim(0, None)
```

这段代码并非完全复现之前的内容，但你可以看到它是基于之前的图表构建的。如果需要，我们可以进一步调整参数，使其与之前的图表完全一致。

让我们简要解释一下这段代码的作用：
1.  我们进行了一些数据筛选。
2.  我们指定了 `hue_order`，这限制了图表中显示的国家。
3.  我们指定了 `palette`，这是一个与 `hue_order` 顺序对应的颜色列表，例如我们指定美国为红色。
4.  我们设置了标题和Y轴的范围。

至此，图表已经相当不错了。当然，我们还可以根据需求进行更多自定义。

---

**总结**

![](img/5303c60389925e7ee8eefeedddd3a563_2.png)

本节课中，我们一起学习了如何使用Seaborn创建折线图。我们了解到，Seaborn可以通过简单的参数（如 `hue`）自动处理数据分组，并通过 `hue_order` 和 `palette` 等参数轻松控制图表的显示顺序和颜色。这使得创建清晰、美观的折线图变得非常高效。