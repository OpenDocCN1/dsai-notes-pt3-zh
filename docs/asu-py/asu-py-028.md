# 28：元组的创建与使用 📚

![](img/21740ea08ebbd97c14ec28e228e304f0_0.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_2.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_3.png)

在本节课中，我们将学习Python中一个重要的数据结构——元组。我们将了解元组的基本概念、如何创建元组、如何对元组进行切片操作，以及如何遍历元组列表。

---

![](img/21740ea08ebbd97c14ec28e228e304f0_5.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_6.png)

## 元组简介

![](img/21740ea08ebbd97c14ec28e228e304f0_8.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_9.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_10.png)

上一节我们介绍了列表，本节中我们来看看元组。与列表不同，元组是**不可变**的数据结构。这意味着一旦创建了元组，就不能再添加、更新或删除其中的元素。

**核心概念**：元组的不可变性
```python
# 元组创建后无法修改
my_tuple = (1, 2, 3)
# my_tuple[0] = 10  # 这行代码会引发错误
```

然而，如果需要对元组进行操作，可以创建该元组的一个副本，然后在副本上进行必要的修改。

![](img/21740ea08ebbd97c14ec28e228e304f0_12.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_13.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_14.png)

---

![](img/21740ea08ebbd97c14ec28e228e304f0_15.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_16.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_18.png)

## 元组的创建与特性

元组是用于在单个变量中存储和操作元素的数据结构。与列表类似，元组可以包含多种数据类型的元素。

以下是创建元组的基本方法：

![](img/21740ea08ebbd97c14ec28e228e304f0_20.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_21.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_22.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_23.png)

*   使用圆括号 `()` 将所有元素括起来，元素之间用逗号 `,` 分隔。
*   即使只有一个元素，也需要在元素后加上逗号，以区别于普通字符串。

![](img/21740ea08ebbd97c14ec28e228e304f0_24.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_26.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_27.png)

**核心概念**：创建元组
```python
# 创建包含多个元素的元组
tuple1 = (1, 2, 3, ‘a‘)
# 创建单个元素的元组（注意逗号）
single_element_tuple = (‘hello‘,)
# 这不是元组，而是字符串
not_a_tuple = (‘hello‘)
```

![](img/21740ea08ebbd97c14ec28e228e304f0_29.png)

元组中的每个值（元素）都可以通过索引来引用，索引从0开始。

![](img/21740ea08ebbd97c14ec28e228e304f0_31.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_33.png)

---

![](img/21740ea08ebbd97c14ec28e228e304f0_35.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_36.png)

## 创建元组的实践

![](img/21740ea08ebbd97c14ec28e228e304f0_38.png)

让我们通过一个例子来实践创建元组的过程。我们将查看一个列表，将其转换为元组，比较字符串和元组，并对元组进行切片。

![](img/21740ea08ebbd97c14ec28e228e304f0_40.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_41.png)

首先，我们创建一个空元组并打印它。

![](img/21740ea08ebbd97c14ec28e228e304f0_43.png)

```python
tuple1 = ()
print(tuple1)  # 输出: ()
```

![](img/21740ea08ebbd97c14ec28e228e304f0_45.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_47.png)

接下来，我们创建一个包含数字的元组。

![](img/21740ea08ebbd97c14ec28e228e304f0_48.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_49.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_51.png)

```python
tuple2 = (12, 32.3, 65, 2, 43)
print(tuple2)  # 输出: (12, 32.3, 65, 2, 43)
```

![](img/21740ea08ebbd97c14ec28e228e304f0_53.png)

现在，我们尝试创建一个看似是元组的变量。

![](img/21740ea08ebbd97c14ec28e228e304f0_55.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_57.png)

```python
tuple3 = (‘ABC‘)
print(type(tuple3))  # 输出: <class ‘str‘>
```

![](img/21740ea08ebbd97c14ec28e228e304f0_58.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_60.png)

如上所示，`type()` 函数告诉我们 `tuple3` 的数据类型是字符串，而不是元组。为了让Python将其识别为元组，我们需要在字符串后加上逗号。

![](img/21740ea08ebbd97c14ec28e228e304f0_62.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_64.png)

```python
tuple4 = (‘ABC‘,)
print(type(tuple4))  # 输出: <class ‘tuple‘>
```

![](img/21740ea08ebbd97c14ec28e228e304f0_66.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_68.png)

接下来，我们将一个字符串转换为元组。可以使用 `tuple()` 函数进行类型转换（或称为“强制转换”）。

![](img/21740ea08ebbd97c14ec28e228e304f0_70.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_72.png)

```python
# 将字符串转换为元组，每个字符成为元组的一个元素
tuple5 = tuple(‘parrot‘)
print(tuple5)  # 输出: (‘p‘, ‘a‘, ‘r‘, ‘r‘, ‘o‘, ‘t‘)
```

![](img/21740ea08ebbd97c14ec28e228e304f0_73.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_75.png)

最后，我们对这个元组进行切片操作。切片时，起始索引包含在结果中，而结束索引不包含在结果中。

![](img/21740ea08ebbd97c14ec28e228e304f0_77.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_79.png)

```python
# 切片操作：获取索引1到4（不包含4）的元素
slice_result = tuple5[1:4]
print(slice_result)  # 输出: (‘a‘, ‘r‘, ‘r‘)
# 索引对应关系: 0:‘p‘, 1:‘a‘, 2:‘r‘, 3:‘r‘, 4:‘o‘, 5:‘t‘
```

![](img/21740ea08ebbd97c14ec28e228e304f0_81.png)

---

![](img/21740ea08ebbd97c14ec28e228e304f0_82.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_84.png)

## 列表与元组的转换

![](img/21740ea08ebbd97c14ec28e228e304f0_86.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_88.png)

上一节我们创建了元组，本节中我们来看看如何将列表转换为元组，并使用循环进行遍历。

![](img/21740ea08ebbd97c14ec28e228e304f0_90.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_92.png)

首先，我们有一个列表。

![](img/21740ea08ebbd97c14ec28e228e304f0_94.png)

```python
my_list = [12, 32.3, 65, 2, 43]
```

![](img/21740ea08ebbd97c14ec28e228e304f0_96.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_97.png)

要将其转换为元组，我们使用 `tuple()` 函数。

![](img/21740ea08ebbd97c14ec28e228e304f0_99.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_100.png)

```python
tuple1 = tuple(my_list)
print(tuple1)           # 输出: (12, 32.3, 65, 2, 43)
print(type(tuple1))     # 输出: <class ‘tuple‘>
```

![](img/21740ea08ebbd97c14ec28e228e304f0_101.png)

我们也可以使用 `for` 循环遍历列表，并在循环中创建元组（尽管更常见的做法是先转换再遍历）。

![](img/21740ea08ebbd97c14ec28e228e304f0_103.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_104.png)

```python
# 此示例演示了遍历列表的想法，但通常直接遍历转换后的元组更简单
for item in my_list:
    temp_tuple = (item,)  # 为每个元素创建一个单元素元组
    # ... 处理 temp_tuple
```

![](img/21740ea08ebbd97c14ec28e228e304f0_106.png)

此外，我们可以使用“解包”操作将元组的元素分配给多个变量。

```python
# 假设有一个元组
data_tuple = (‘Bob‘, 1001, 1500.75)
# 解包元组
name, account_id, balance = data_tuple
print(name, account_id, balance)  # 输出: Bob 1001 1500.75
```

---

## 元组的切片操作

现在，让我们更深入地探讨元组的切片操作。我们定义一个元组并查看不同的切片方式。

![](img/21740ea08ebbd97c14ec28e228e304f0_108.png)

```python
my_tuple = (12, 32.3, 65, 2, 43, 86)
print(‘原始元组:‘, my_tuple)  # 输出: (12, 32.3, 65, 2, 43, 86)
```

**切片示例1**：获取索引1到5（不包含5）的元素。

```python
print(my_tuple[1:5])  # 输出: (32.3, 65, 2, 43)
```

**切片示例2**：从开始到索引4（不包含4）。

```python
print(my_tuple[:4])   # 输出: (12, 32.3, 65, 2)
```

![](img/21740ea08ebbd97c14ec28e228e304f0_110.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_111.png)

**切片示例3**：从索引2到结尾。

```python
print(my_tuple[2:])   # 输出: (65, 2, 43, 86)
```

![](img/21740ea08ebbd97c14ec28e228e304f0_113.png)

**切片示例4**：获取整个元组（两种等效方式）。

![](img/21740ea08ebbd97c14ec28e228e304f0_114.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_116.png)

```python
print(my_tuple[:])    # 输出: (12, 32.3, 65, 2, 43, 86)
print(my_tuple)       # 输出: (12, 32.3, 65, 2, 43, 86)
```

![](img/21740ea08ebbd97c14ec28e228e304f0_118.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_119.png)

**切片示例5**：使用步长。格式为 `[start:stop:step]`。以下示例从开始到结尾，每隔一个元素取一个。

![](img/21740ea08ebbd97c14ec28e228e304f0_121.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_123.png)

```python
print(my_tuple[::2])  # 输出: (12, 65, 43)
# 过程: 索引0(12) -> 跳过索引1 -> 索引2(65) -> 跳过索引3 -> 索引4(43) -> 跳过索引5
```

![](img/21740ea08ebbd97c14ec28e228e304f0_125.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_127.png)

---

![](img/21740ea08ebbd97c14ec28e228e304f0_129.png)

## 遍历元组列表

![](img/21740ea08ebbd97c14ec28e228e304f0_130.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_132.png)

我们经常需要处理由元组组成的列表。例如，一个存储账户信息的列表，每个账户信息是一个元组（姓名，账号，余额）。

![](img/21740ea08ebbd97c14ec28e228e304f0_134.png)

以下是遍历这种结构的方法。

![](img/21740ea08ebbd97c14ec28e228e304f0_136.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_137.png)

首先，创建一个元组列表。

![](img/21740ea08ebbd97c14ec28e228e304f0_139.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_141.png)

```python
accounts = [
    (‘Bob‘, 1001, 1500.75),
    (‘Sam‘, 1002, 2200.50),
    (‘Tina‘, 1003, 1800.00),
    (‘Lisa‘, 1004, 950.25)
]
```

![](img/21740ea08ebbd97c14ec28e228e304f0_143.png)

**方法一：使用嵌套的 `for` 循环**

![](img/21740ea08ebbd97c14ec28e228e304f0_145.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_146.png)

要打印列表中的每个元组的每个元素，我们需要使用嵌套循环：外层循环遍历列表，内层循环遍历每个元组。

![](img/21740ea08ebbd97c14ec28e228e304f0_148.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_149.png)

```python
for account in accounts:      # 遍历列表中的每个元组
    for element in account:   # 遍历当前元组中的每个元素
        print(element, end=‘ ‘)  # 打印元素，以空格分隔
    print()                   # 每个元组后换行
# 输出:
# Bob 1001 1500.75
# Sam 1002 2200.50
# Tina 1003 1800.00
# Lisa 1004 950.25
```

![](img/21740ea08ebbd97c14ec28e228e304f0_151.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_153.png)

**方法二：使用 `enumerate` 函数**

![](img/21740ea08ebbd97c14ec28e228e304f0_155.png)

`enumerate` 函数可以在遍历的同时获取元素的索引。这对于需要位置信息的情况很有用。

![](img/21740ea08ebbd97c14ec28e228e304f0_157.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_159.png)

```python
for index, account_tuple in enumerate(accounts):
    # account_tuple 是一个元组，如 (‘Bob‘, 1001, 1500.75)
    print(f“索引 {index}: 姓名 {account_tuple[0]}, 账号 {account_tuple[1]}, 余额 {account_tuple[2]}“)
# 输出:
# 索引 0: 姓名 Bob, 账号 1001, 余额 1500.75
# 索引 1: 姓名 Sam, 账号 1002, 余额 2200.50
# 索引 2: 姓名 Tina, 账号 1003, 余额 1800.00
# 索引 3: 姓名 Lisa, 账号 1004, 余额 950.25
```

![](img/21740ea08ebbd97c14ec28e228e304f0_161.png)

---

![](img/21740ea08ebbd97c14ec28e228e304f0_163.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_164.png)

## 总结

![](img/21740ea08ebbd97c14ec28e228e304f0_166.png)

![](img/21740ea08ebbd97c14ec28e228e304f0_167.png)

本节课中我们一起学习了Python中元组的基本知识。我们了解到元组是一种**不可变**的序列，使用圆括号定义。我们掌握了创建元组、将列表转换为元组、对元组进行切片以及遍历元组列表的方法。记住，元组的不可变性使其适用于存储不应被程序意外修改的数据。在下一节课中，我们将通过更多演示来练习元组的实际应用。