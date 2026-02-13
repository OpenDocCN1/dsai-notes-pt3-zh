# 117：字典累积导论 📚

## 概述

在本节课中，我们将学习字典累积模式。这一模式结合了字典和累积器模式，使两者变得更加强大。我们将要学习的并非新的Python类型或结构，而是一种通过扩展累积器模式来使用任意数量累积变量的技术，用以解决多种问题。

作为预览，我们将利用字典中的键值对来追踪任意数量的累积变量。我们将主要通过示例和问题来深入了解这一模式。

现在，让我们开始学习。

![](img/51d254ba40dc73a2c8187e3cc8326f4e_0.png)

---

![](img/51d254ba40dc73a2c8187e3cc8326f4e_1.png)

## 字典累积模式简介

上一节我们介绍了累积器的基本概念，本节中我们来看看如何将其与字典结合。

字典累积模式的核心思想是：使用一个字典作为累积器，字典的键用于标识不同的类别或项目，而对应的值则用于累积（例如计数、求和等）。这允许我们在单个数据结构中管理多个独立的累积变量。

其基本公式可以表示为：
```
accumulator_dict = {}
for item in data:
    key = get_key(item)        # 确定当前项对应的键
    current_value = accumulator_dict.get(key, initial_value)  # 获取当前累积值，若无则使用初始值
    new_value = update_function(current_value, item)           # 根据当前项更新值
    accumulator_dict[key] = new_value                          # 将新值存回字典
```

---

## 应用示例：统计单词频率

让我们通过一个具体例子来理解这个模式。假设我们需要统计一段文本中每个单词出现的次数。

以下是实现步骤：

1.  初始化一个空字典作为累积器。
2.  遍历文本中的每个单词。
3.  对于每个单词，检查它是否已经是字典的键。
    *   如果是，将其对应的值（计数）加1。
    *   如果不是，则将该单词作为新键加入字典，并设置其初始值为1。

对应的Python代码如下：
```python
text = "apple banana apple orange banana apple"
word_counts = {}  # 初始化累积字典

words = text.split()
for word in words:
    # 使用 .get() 方法，如果键不存在则返回默认值0
    word_counts[word] = word_counts.get(word, 0) + 1

print(word_counts)  # 输出：{'apple': 3, 'banana': 2, 'orange': 1}
```

---

## 模式的一般步骤

基于上面的例子，我们可以总结出字典累积模式的一般步骤。

以下是该模式的通用流程：

1.  **初始化累积字典**：创建一个空字典 `accumulator = {}`。
2.  **遍历数据**：使用循环遍历数据集中的每一项。
3.  **确定键**：根据当前项，确定其在累积字典中对应的键。
4.  **更新值**：
    *   使用 `accumulator.get(key, default_value)` 安全地获取当前累积值。
    *   根据业务逻辑（如加1、累加、追加到列表等）计算新值。
5.  **存储结果**：将新值赋值回字典：`accumulator[key] = new_value`。

---

## 另一个例子：按类别分组

除了计数，此模式还可用于分组。例如，将一系列人员按其所在城市分组。

以下是实现代码：
```python
people = [('Alice', 'New York'), ('Bob', 'Chicago'), ('Charlie', 'New York'), ('David', 'Chicago')]
city_groups = {}

for name, city in people:
    # 如果城市键不存在，则初始化为一个空列表
    if city not in city_groups:
        city_groups[city] = []
    # 将姓名添加到对应城市的列表中
    city_groups[city].append(name)

print(city_groups)
# 输出：{'New York': ['Alice', 'Charlie'], 'Chicago': ['Bob', 'David']}
```

---

## 总结

本节课中我们一起学习了字典累积模式。我们了解到，通过将字典作为累积器，我们可以灵活地追踪和更新多个与不同键相关联的累积值。这种模式在数据统计、分组和聚合等场景中非常有用。关键在于：**初始化字典、遍历数据、为每项确定键、安全地更新对应的值**。掌握这一模式将极大地提升你处理复杂数据聚合任务的能力。