# 🎲 课程 P15：Python 随机模块 (random) 入门教程

![](img/d599875aee7f49738a513fca7cd6b5ba_0.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_2.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_3.png)

在本节课中，我们将学习如何使用 Python 的 `random` 模块为程序引入随机性或概率元素。我们将通过一个模拟发牌的程序来演示该模块的核心功能。

![](img/d599875aee7f49738a513fca7cd6b5ba_4.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_5.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_6.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_7.png)

## 概述

![](img/d599875aee7f49738a513fca7cd6b5ba_9.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_10.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_11.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_12.png)

`random` 模块是 Python 的内置模块，它提供了多种函数来生成随机数或进行随机选择。通过本教程，你将学会如何导入该模块，并使用 `choice`、`choices`、`sample` 等函数进行随机选择，了解“有放回”与“无放回”抽样的区别，学习如何为选择设置权重，以及如何使用随机种子 (`seed`) 来确保程序在调试时可复现。

![](img/d599875aee7f49738a513fca7cd6b5ba_14.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_15.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_16.png)

## 导入模块与基础示例

首先，我们需要导入 `random` 模块。我们将创建一个名为 `cards.py` 的程序，它模拟从一个包含三张牌（J、Q、K）的列表中随机发牌。

![](img/d599875aee7f49738a513fca7cd6b5ba_18.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_19.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_20.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_21.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_22.png)

```python
import random

![](img/d599875aee7f49738a513fca7cd6b5ba_23.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_24.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_25.png)

cards = ["Jack", "Queen", "King"]
```

## 随机选择单个元素：`choice` 函数

![](img/d599875aee7f49738a513fca7cd6b5ba_27.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_28.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_29.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_30.png)

`random.choice()` 函数接收一个列表作为输入，并随机返回列表中的一个元素。

![](img/d599875aee7f49738a513fca7cd6b5ba_31.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_32.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_33.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_34.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_35.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_36.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_37.png)

以下是使用 `choice` 函数的代码示例：

![](img/d599875aee7f49738a513fca7cd6b5ba_38.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_40.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_41.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_42.png)

```python
card = random.choice(cards)
print(card)
```

运行程序，每次可能会得到 `"Jack"`、`"Queen"` 或 `"King"` 中的任意一个，结果完全随机。

## 随机选择多个元素：`choices` 函数

![](img/d599875aee7f49738a513fca7cd6b5ba_44.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_45.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_46.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_47.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_48.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_49.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_50.png)

上一节我们介绍了如何随机选择单个元素。本节中我们来看看如何一次性选择多个元素。`random.choices()` 函数允许我们从列表中随机选择指定数量的元素，并且默认进行**有放回**抽样。

![](img/d599875aee7f49738a513fca7cd6b5ba_51.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_52.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_53.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_54.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_55.png)

该函数接受两个主要参数：
1.  待选择的列表。
2.  `k`：指定要选择的元素数量。

![](img/d599875aee7f49738a513fca7cd6b5ba_57.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_58.png)

以下是使用 `choices` 函数选择两张牌的代码：

```python
selected_cards = random.choices(cards, k=2)
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_60.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_61.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_62.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_63.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_64.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_65.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_66.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_67.png)

运行程序，你可能会得到 `['Queen', 'King']` 或 `['Jack', 'Jack']` 等结果。注意，由于是有放回抽样，结果中可能出现重复元素。

![](img/d599875aee7f49738a513fca7cd6b5ba_68.png)

## 无放回随机抽样：`sample` 函数

![](img/d599875aee7f49738a513fca7cd6b5ba_70.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_71.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_72.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_73.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_74.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_75.png)

`random.choices()` 函数进行的是有放回抽样。如果我们希望进行无放回抽样（即抽出的元素不再放回原集合），可以使用 `random.sample()` 函数。

`random.sample()` 函数的参数与 `choices` 类似，但它确保在选择的 `k` 个元素中不会有重复（前提是原列表本身没有重复，且 `k` 不大于列表长度）。

![](img/d599875aee7f49738a513fca7cd6b5ba_77.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_78.png)

以下是使用 `sample` 函数的代码：

![](img/d599875aee7f49738a513fca7cd6b5ba_79.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_80.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_81.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_82.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_83.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_84.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_85.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_86.png)

```python
selected_cards = random.sample(cards, k=2)
print(selected_cards)
```

运行程序，结果总是两张不同的牌，例如 `['Queen', 'King']` 或 `['Jack', 'Queen']`。

![](img/d599875aee7f49738a513fca7cd6b5ba_88.png)

## 为选择设置权重

![](img/d599875aee7f49738a513fca7cd6b5ba_89.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_90.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_91.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_92.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_93.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_94.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_95.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_96.png)

`random.choices()` 函数还允许我们通过 `weights` 参数为列表中的每个元素设置被选中的权重，从而控制概率。

![](img/d599875aee7f49738a513fca7cd6b5ba_97.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_99.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_100.png)

`weights` 参数接收一个数字列表，其长度必须与待选择的列表相同。每个数字代表对应元素被选中的相对权重。

以下是为三张牌设置不同权重的示例。假设我们希望抽到 Jack 的概率是 75%，Queen 是 20%，King 是 5%：

![](img/d599875aee7f49738a513fca7cd6b5ba_102.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_103.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_104.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_105.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_106.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_107.png)

```python
selected_cards = random.choices(cards, weights=[75, 20, 5], k=2)
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_109.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_110.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_111.png)

多次运行程序，你会发现结果中出现 `Jack` 的频率远高于其他牌。

![](img/d599875aee7f49738a513fca7cd6b5ba_112.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_113.png)

## 使用随机种子确保可复现性

随机性虽然有用，但在调试程序时，不可预测的结果会增加难度。`random` 模块提供了 `seed()` 函数来初始化伪随机数生成器。只要使用相同的种子 (`seed`)，程序每次运行都会产生相同的“随机”序列，这非常利于调试。

![](img/d599875aee7f49738a513fca7cd6b5ba_115.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_116.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_117.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_118.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_119.png)

你可以通过 `random.seed()` 来设置种子，通常传入一个整数。

![](img/d599875aee7f49738a513fca7cd6b5ba_120.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_121.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_122.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_123.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_124.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_125.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_126.png)

以下是设置种子的代码示例：

![](img/d599875aee7f49738a513fca7cd6b5ba_128.png)

```python
random.seed(0) # 设置随机种子为 0
selected_cards = random.choices(cards, k=2)
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_130.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_131.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_132.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_133.png)

无论你运行程序多少次，只要种子是 `0`，输出的结果将始终保持一致（例如，可能是 `['King', 'King']`）。如果将种子改为 `1`，则会得到另一组固定不变的结果。

![](img/d599875aee7f49738a513fca7cd6b5ba_135.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_136.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_138.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_139.png)

## 总结

![](img/d599875aee7f49738a513fca7cd6b5ba_141.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_142.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_143.png)

本节课中我们一起学习了 Python `random` 模块的核心用法。我们掌握了如何使用 `choice` 进行单项随机选择，使用 `choices` 进行有放回的多项选择并可通过 `weights` 设置权重，使用 `sample` 进行无放回的多项选择。最后，我们还学习了如何使用 `seed` 函数设置随机种子，以确保在需要调试时，程序的随机行为是可预测和可复现的。利用这些工具，你可以轻松地为程序添加各种随机化功能。