# 课程3：Python 3编程 - P32：31_03_04_zip函数总结 🧵

![](img/ac3d622860fb566cdd82e4beb8f9a86a_0.png)

在本节课中，我们将学习Python内置的`zip`函数。这个函数允许我们将多个可迭代对象（如列表）的元素配对组合，是进行并行迭代和操作的强大工具。

![](img/ac3d622860fb566cdd82e4beb8f9a86a_1.png)

上一节我们介绍了列表推导式等高级操作，本节中我们来看看如何使用`zip`函数来同步处理多个序列。

## `zip`函数概述

`zip`函数接收多个可迭代对象作为参数，并返回一个迭代器。该迭代器生成一系列元组，其中每个元组包含来自各个输入可迭代对象的、处于相同位置的元素。

其核心行为可以用以下伪代码描述：
```
zip(iter1, iter2, ...) -> 生成 (item1, item2, ...) 的迭代器
```
其中`item1`来自`iter1`，`item2`来自`iter2`，依此类推。

## `zip`函数的典型应用场景

`zip`函数适用于任何需要进行成对操作的场景。

例如，假设你有三个单词列表，需要生成一个新列表，该列表的每个元素是三个列表中对应位置的最长单词。

以下是解决此问题的步骤：

首先，使用`zip`函数将三个列表组合成一个元组列表。
```python
list1 = ["apple", "dog", "computer"]
list2 = ["banana", "cat", "laptop"]
list3 = ["cherry", "elephant", "PC"]

zipped = zip(list1, list2, list3)
# 此时 zipped 是一个迭代器，内容类似于：
# [('apple', 'banana', 'cherry'), ('dog', 'cat', 'elephant'), ('computer', 'laptop', 'PC')]
```

接着，你可以使用列表推导式进行映射操作，将每个包含三个单词的元组转换为单个字符串，即其中最长的单词。
```python
longest_words = [max(word_tuple, key=len) for word_tuple in zipped]
# 结果：['banana', 'elephant', 'computer']
```

## 总结

本节课中我们一起学习了`zip`函数。我们了解到，`zip`是一个用于将多个序列中对应位置的元素配对组合的便捷工具。通过结合列表推导式，我们可以轻松地对这些配对元素进行复杂的转换和处理，例如找出每组中的最大值。掌握`zip`函数能让你在处理多个相关数据序列时更加高效。