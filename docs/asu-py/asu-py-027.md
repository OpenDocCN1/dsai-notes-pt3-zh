# 27：列表的创建与使用 📋

![](img/7290531c06c0b30bfc98189ffed4d27a_1.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_2.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_3.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_5.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_7.png)

在本节课中，我们将要学习Python中一个非常重要的数据结构——列表。我们将从列表的基本概念开始，逐步学习如何创建、修改、访问和操作列表中的数据。

![](img/7290531c06c0b30bfc98189ffed4d27a_9.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_10.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_11.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_12.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_14.png)

## 什么是列表？🤔

![](img/7290531c06c0b30bfc98189ffed4d27a_16.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_18.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_20.png)

我们需要一种简单的方法来存储多个独立的项目，而不需要为每个项目创建大量不同的变量名。例如，如果要记录学生的成绩，为每个学生创建一个变量会非常繁琐。

![](img/7290531c06c0b30bfc98189ffed4d27a_22.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_23.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_25.png)

```python
bob_grade = 94
cindy_grade = 42
jan_grade = 74
```

![](img/7290531c06c0b30bfc98189ffed4d27a_26.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_27.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_29.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_31.png)

如果要记录100个成绩，这种方法将变得非常困难。列表可以解决这个问题。我们可以创建一个列表变量，并将所有不同的成绩都分配给它。

![](img/7290531c06c0b30bfc98189ffed4d27a_33.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_34.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_36.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_37.png)

列表使用方括号 `[]` 来标识其中的元素，每个值之间用逗号分隔。

![](img/7290531c06c0b30bfc98189ffed4d27a_39.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_40.png)

## 创建与初始化列表 🛠️

列表可以被看作一个索引数组。索引从0开始，0是第一个元素的位置。

![](img/7290531c06c0b30bfc98189ffed4d27a_42.png)

以下是如何创建列表的示例：

```python
list1 = [‘mic‘, 123, 123.4, ‘Sam‘, 34.1]
list2 = [123.0, ‘James‘, ‘10‘]
list3 = [12, 32.3, 65, 2, 43]
```

在这个例子中，`list1` 混合了不同的数据类型：字符串、整数和浮点数。在Python中，整数是没有小数点的数字，浮点数是有小数点的数字，字符串是一系列字符。Python不区分单引号和双引号，两者都识别为字符串。

![](img/7290531c06c0b30bfc98189ffed4d27a_44.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_46.png)

要显示这些列表，只需使用 `print` 命令。

![](img/7290531c06c0b30bfc98189ffed4d27a_48.png)

```python
print(list1)
print(list2)
print(list3)
```

![](img/7290531c06c0b30bfc98189ffed4d27a_50.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_52.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_54.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_55.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_57.png)

## 向列表添加元素 ➕

![](img/7290531c06c0b30bfc98189ffed4d27a_59.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_61.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_62.png)

上一节我们介绍了如何创建列表，本节中我们来看看如何向列表中添加新元素。

![](img/7290531c06c0b30bfc98189ffed4d27a_64.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_65.png)

以下是向列表添加元素的几种方法：

![](img/7290531c06c0b30bfc98189ffed4d27a_67.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_69.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_71.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_73.png)

*   **拼接列表**：使用 `+` 运算符可以将两个列表合并。
    ```python
    list4 = list1 + list2
    ```
*   **追加元素**：使用 `.append()` 方法可以在列表末尾添加一个元素。
    ```python
    list1.append(‘A,B,C‘)
    ```
*   **插入元素**：使用 `.insert()` 方法可以在列表的指定索引位置插入一个元素。它需要两个参数：索引位置和要插入的值。
    ```python
    list3.insert(2, 12)  # 在索引2的位置插入数字12
    ```
*   **扩展列表**：使用 `.extend()` 方法可以在列表末尾添加多个元素（通常是另一个列表中的元素）。
    ```python
    list2.extend([7, 6, 5])
    ```

![](img/7290531c06c0b30bfc98189ffed4d27a_75.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_76.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_78.png)

## 访问与切片列表中的数据 🔍

![](img/7290531c06c0b30bfc98189ffed4d27a_80.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_82.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_84.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_86.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_88.png)

创建和修改列表后，我们需要从中获取数据。可以通过索引直接访问单个元素，也可以通过切片获取一个范围内的元素。

![](img/7290531c06c0b30bfc98189ffed4d27a_90.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_92.png)

以下是访问列表元素的几种方式：

![](img/7290531c06c0b30bfc98189ffed4d27a_94.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_96.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_97.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_98.png)

*   **访问单个元素**：使用 `列表名[索引]` 的格式。索引从0开始。
    ```python
    x = list1[0]  # 获取list1的第一个元素，即 ‘mic‘
    ```
*   **切片操作**：使用冒号 `:` 来指定一个范围。格式为 `[起始索引:结束索引]`，结果包含起始索引的元素，但不包含结束索引的元素。
    ```python
    y = list1[1:3]  # 获取list1中索引1和2的元素，即 [123, 123.4]
    ```
*   **获取到末尾的所有元素**：如果省略结束索引，切片会一直取到列表末尾。
    ```python
    z = list1[2:]   # 获取list1中从索引2开始到末尾的所有元素
    ```

![](img/7290531c06c0b30bfc98189ffed4d27a_100.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_101.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_103.png)

## 排序与反转列表 🔄

![](img/7290531c06c0b30bfc98189ffed4d27a_105.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_107.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_108.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_110.png)

很多时候我们需要对列表进行排序，以便快速搜索值。Python提供了简单的方法来排序和反转列表。

![](img/7290531c06c0b30bfc98189ffed4d27a_112.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_114.png)

以下是列表排序和反转的操作：

![](img/7290531c06c0b30bfc98189ffed4d27a_115.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_117.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_118.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_120.png)

*   **反转列表**：使用 `.reverse()` 方法可以反转列表中元素的顺序。
    ```python
    list1.reverse()
    ```
*   **排序列表**：使用 `.sort()` 方法可以对列表进行升序排序。**非常重要的一点是**：如果列表混合了不同的数据类型（如字符串和数字），排序操作会导致错误。因此，在使用排序方法时，请确保列表中的元素是单一的数据类型。
    ```python
    list3.sort()  # 对数字列表排序
    names_list = [‘Mike‘, ‘Tina‘, ‘Sam‘]
    names_list.sort()  # 对字符串列表按字母顺序排序
    ```

![](img/7290531c06c0b30bfc98189ffed4d27a_122.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_123.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_125.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_127.png)

## 其他列表操作 ⚙️

![](img/7290531c06c0b30bfc98189ffed4d27a_129.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_130.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_131.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_133.png)

除了添加、访问和排序，列表还支持其他有用的操作。

![](img/7290531c06c0b30bfc98189ffed4d27a_135.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_137.png)

以下是一些常用的列表操作：

![](img/7290531c06c0b30bfc98189ffed4d27a_139.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_140.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_142.png)

*   **查找索引**：使用 `.index(元素)` 方法可以查找某个元素在列表中首次出现的索引位置。
    ```python
    position = list3.index(65)
    ```
*   **统计元素出现次数**：使用 `.count(元素)` 方法可以统计某个元素在列表中出现的次数。
    ```python
    count_of_twos = list3.count(2)
    ```
*   **移除元素**：使用 `.remove(元素)` 方法可以移除列表中首次出现的指定元素。如果要移除所有匹配的元素，需要先统计次数，然后使用循环。
    ```python
    list3.remove(2)  # 只移除第一个2
    ```
*   **再次使用切片**：切片是获取列表子集的强大工具。
    ```python
    sub_list = list3[1:3]
    ```

![](img/7290531c06c0b30bfc98189ffed4d27a_144.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_146.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_147.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_148.png)

## 显示列表数据 📺

![](img/7290531c06c0b30bfc98189ffed4d27a_150.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_151.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_152.png)

到目前为止，我们一直使用 `print` 函数来显示整个列表，这是最常见的方式。

![](img/7290531c06c0b30bfc98189ffed4d27a_154.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_156.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_157.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_159.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_160.png)

显示列表数据有多种方式：

![](img/7290531c06c0b30bfc98189ffed4d27a_162.png)

*   使用 `print(列表名)` 打印整个列表。
*   使用 `print(列表名[索引])` 打印单个元素。
*   使用切片打印多个元素，如 `print(列表名[1:4])`。
*   将列表元素或操作结果赋值给变量，然后打印该变量。

![](img/7290531c06c0b30bfc98189ffed4d27a_164.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_165.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_166.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_167.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_168.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_170.png)

## 总结 📝

![](img/7290531c06c0b30bfc98189ffed4d27a_172.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_173.png)

![](img/7290531c06c0b30bfc98189ffed4d27a_174.png)

本节课中我们一起学习了Python列表的核心知识。我们了解了列表是一种用于存储多个项目的高效数据结构。我们学习了如何创建包含不同数据类型的列表，如何使用 `.append()`, `.insert()`, `.extend()` 方法添加元素，以及如何使用 `+` 拼接列表。我们掌握了通过索引和切片来访问列表中的元素。我们还探讨了如何使用 `.sort()` 和 `.reverse()` 方法对列表进行排序和反转，并强调了排序时数据类型必须一致。最后，我们介绍了其他实用操作，如查找索引 (`.index()`)、统计次数 (`.count()`)、移除元素 (`.remove()`) 以及多种显示列表内容的方法。列表是Python编程的基石，熟练掌握它们对后续学习至关重要。