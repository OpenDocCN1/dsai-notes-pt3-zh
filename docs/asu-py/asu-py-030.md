# 30：集合的创建与使用 📚

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_0.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_2.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_3.png)

在本节课中，我们将要学习Python中一个重要的数据结构——**集合（Set）**。我们将了解集合的基本概念、如何创建集合、如何遍历集合，以及集合的各种操作和内置函数。集合在处理唯一元素和进行数学集合运算时非常有用。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_5.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_6.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_8.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_10.png)

## 集合简介 🧩

集合是一个**无序的、可迭代的、可变的**元素集合。它最重要的特性是**不允许重复元素**。集合在Python中也被称为哈希函数。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_12.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_13.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_14.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_15.png)

集合的定义可以概括为以下几点：
*   它是一个无序的元素集合。
*   每个元素必须是**唯一的**。
*   集合中的元素本身必须是**不可变的**（例如数字、字符串、元组）。
*   重复的元素会被自动消除。
*   集合本身是**可变的**，我们可以向其中添加或删除元素，改变其状态、长度和内容。
*   集合可用于执行数学集合运算，如并集、交集、对称差集等。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_16.png)

需要记住的是，**集合不支持任何形式的索引**。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_18.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_19.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_20.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_22.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_24.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_26.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_27.png)

## 创建集合 🔨

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_29.png)

上一节我们介绍了集合的基本概念，本节中我们来看看如何创建集合。我们可以通过多种方式创建集合：创建一个空集合、直接定义集合、或者使用`set()`方法。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_31.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_32.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_34.png)

以下是创建集合的几种方法：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_36.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_38.png)

*   **使用花括号定义**：`my_set = {11, 22, 33, 44}`
*   **使用`set()`构造函数**：`my_set = set([1, 2, 3])`
*   **创建空集合**：必须使用`set()`，因为`{}`创建的是空字典。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_40.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_42.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_44.png)

让我们通过代码来具体看看：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_45.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_47.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_49.png)

```python
# 示例1：使用花括号创建集合，并观察自动去重
set1 = {11, 11, 22, 33, 44}
print(set1)  # 输出：{33, 11, 44, 22} （顺序可能不同，且第二个11被移除）

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_51.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_53.png)

# 示例2：使用set()构造函数创建集合
set2 = set((1, 2, 3))
print(set2)  # 输出：{1, 2, 3}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_54.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_56.png)

# 示例3：使用set()将列表转换为集合
set3 = set([1, 2, 3])
print(set3)  # 输出：{1, 2, 3}
```

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_58.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_60.png)

我们还可以使用`range()`函数来快速生成数字集合。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_62.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_63.png)

以下是使用`range()`创建集合的几种方式：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_64.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_65.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_67.png)

*   `set(range(6))`：生成 `{0, 1, 2, 3, 4, 5}`
*   `set(range(2, 6))`：生成 `{2, 3, 4, 5}`
*   `set(range(1, 12, 2))`：从1开始，到12结束（不包含12），步长为2，生成 `{1, 3, 5, 7, 9, 11}`
*   `set(range(-1, -12, -2))`：使用负数步长，生成 `{-11, -9, -7, -5, -3, -1}`

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_69.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_71.png)

注意，在最后一个例子中，输出顺序看起来是“反向”的（从-11到-1），这是因为在数轴上，-11比-9更小（更靠左）。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_73.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_74.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_76.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_78.png)

## 遍历集合 🔄

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_80.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_82.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_83.png)

既然集合是可迭代的，我们就可以使用循环来遍历其中的所有元素。这通常通过`for`循环来实现。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_85.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_87.png)

```python
people = {"Britt", "Sam", "Tim", "Jan"}
for person in people:
    print(f"Great job, {person}!")
```
这段代码会依次（但顺序不固定）输出对集合中每个人的赞美。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_89.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_91.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_93.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_95.png)

## 集合的修改操作 🛠️

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_97.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_99.png)

前面提到集合本身是可变的。接下来，我们看看如何修改一个集合。主要包括添加、更新、移除和清空元素。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_101.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_102.png)

以下是集合常用的修改方法：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_104.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_106.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_107.png)

*   **`add(element)`**：向集合中添加一个元素。
*   **`update(iterable)`**：将一个字符串、集合、元组、列表或字典的所有元素添加到当前集合中。
*   **`pop()`**：随机移除并返回集合中的一个元素。
*   **`remove(element)`**：移除集合中指定的元素。如果元素不存在，会引发KeyError错误。
*   **`clear()`**：清空集合中的所有元素。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_109.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_111.png)

让我们通过代码示例来理解：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_113.png)

```python
# 初始集合
my_set = {11, 22, 33, 44, 55}
print("初始集合:", my_set)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_115.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_116.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_118.png)

# 1. 使用 add() 添加元素
my_set.add(66)
print("添加66后:", my_set)  # 66被随机插入到某个位置

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_120.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_121.png)

# 2. 使用 update() 添加多个元素
my_set.update([77, 88, 99])
print("更新[77,88,99]后:", my_set)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_123.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_125.png)

# 3. 使用 remove() 移除指定元素
my_set.remove(77)
print("移除77后:", my_set)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_127.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_129.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_131.png)

# 4. 使用 pop() 移除一个元素（随机，但常是“第一个”）
popped_item = my_set.pop()
print(f"被pop的元素是: {popped_item}")
print("pop后:", my_set)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_133.png)

# 5. 使用 clear() 清空集合
my_set.clear()
print("清空后:", my_set)  # 输出：set()
```

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_135.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_136.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_138.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_139.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_141.png)

## 集合运算 🧮

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_143.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_145.png)

集合的强大之处在于可以方便地进行数学集合运算。这些操作可以帮助我们比较两个集合之间的关系，或者组合它们。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_146.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_148.png)

以下是核心的集合运算方法：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_149.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_151.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_152.png)

*   **`union(set2)`** 或 **`|`**：返回两个集合的**并集**（所有不重复的元素）。
    *   **公式**：`A ∪ B`
*   **`intersection(set2)`** 或 **`&`**：返回两个集合的**交集**（同时存在于两个集合中的元素）。
    *   **公式**：`A ∩ B`
*   **`difference(set2)`** 或 **`-`**：返回**差集**（存在于第一个集合但不在第二个集合中的元素）。
    *   **公式**：`A - B`
*   **`symmetric_difference(set2)`** 或 **`^`**：返回**对称差集**（只存在于其中一个集合中的元素）。
    *   **公式**：`(A ∪ B) - (A ∩ B)` 或 `(A - B) ∪ (B - A)`
*   **`isdisjoint(set2)`**：如果两个集合没有共同元素（交集为空），则返回`True`。
*   **`issubset(set2)`** 或 **`<=`**：如果当前集合是另一个集合的**子集**，则返回`True`。
    *   **公式**：`A ⊆ B`
*   **`issuperset(set2)`** 或 **`>=`**：如果当前集合是另一个集合的**超集**，则返回`True`。
    *   **公式**：`A ⊇ B`
*   **`discard(element)`**：移除指定元素，如果元素不存在，**不会**报错（与`remove`的区别）。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_154.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_156.png)

```python
set_a = {11, 22, 33, 44, 55}
set_b = {11, 33, 55, 77, 99}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_158.png)

print("集合A:", set_a)
print("集合B:", set_b)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_160.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_161.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_162.png)

# 并集
print("A和B的并集:", set_a.union(set_b))  # 输出：{33, 99, 11, 44, 77, 22, 55}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_163.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_164.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_166.png)

# 交集
print("A和B的交集:", set_a.intersection(set_b))  # 输出：{33, 11, 55}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_168.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_170.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_171.png)

# 差集 (A - B)
print("A和B的差集(A-B):", set_a.difference(set_b))  # 输出：{44, 22}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_173.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_175.png)

# 对称差集
print("A和B的对称差集:", set_a.symmetric_difference(set_b))  # 输出：{99, 44, 22, 77}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_176.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_177.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_179.png)

# 是否无交集
print("A和B是否无交集:", set_a.isdisjoint(set_b))  # 输出：False

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_181.png)

# 子集与超集检查
print("A是B的子集吗:", set_a.issubset(set_b))  # 输出：False
print("A是B的超集吗:", set_a.issuperset(set_b))  # 输出：False

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_182.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_183.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_185.png)

# 安全移除元素
set_a.discard(55)
print("从A中discard 55后:", set_a)
```

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_187.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_189.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_190.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_192.png)

## 集合的内置函数 ⚙️

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_194.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_196.png)

除了方法，Python还提供了一些内置函数来处理集合，可以方便地获取集合的信息。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_198.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_199.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_201.png)

以下是适用于集合的常用内置函数：

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_203.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_204.png)

*   **`len(set)`**：返回集合中元素的个数。
*   **`max(set)`**：返回集合中最大的元素。
*   **`min(set)`**：返回集合中最小的元素。
*   **`sorted(set)`**：返回一个由集合元素排序后组成的**新列表**（集合本身仍无序）。
*   **`sum(set)`**：返回集合中所有元素的总和（仅当元素为数字时）。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_206.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_208.png)

```python
numbers_set = {11, 22, 44, 55, 33}

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_210.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_212.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_214.png)

print("集合:", numbers_set)
print("元素个数:", len(numbers_set))      # 输出：5
print("最大值:", max(numbers_set))        # 输出：55
print("最小值:", min(numbers_set))        # 输出：11
print("排序后的列表:", sorted(numbers_set)) # 输出：[11, 22, 33, 44, 55]
print("元素总和:", sum(numbers_set))       # 输出：165 (11+22+33+44+55)
```

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_215.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_217.png)

---

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_218.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_220.png)

## 总结 📝

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_222.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_223.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_225.png)

本节课中我们一起学习了Python中**集合（Set）**的全面知识。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_227.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_229.png)

我们首先了解了集合的核心特性：**无序、元素唯一、可变本身但元素不可变**。接着，我们掌握了使用花括号`{}`和`set()`函数**创建集合**的多种方式，包括利用`range()`快速生成数值集合。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_231.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_232.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_234.png)

然后，我们学习了如何通过`for`循环**遍历集合**，以及使用`add()`、`update()`、`remove()`、`pop()`和`clear()`等方法**修改集合**的内容。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_236.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_238.png)

课程的重点在于**集合运算**，我们详细讲解了并集(`union`)、交集(`intersection`)、差集(`difference`)、对称差集(`symmetric_difference`)等操作，以及判断集合关系的`isdisjoint`、`issubset`和`issuperset`方法。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_240.png)

最后，我们介绍了一些实用的**集合内置函数**，如`len()`、`max()`、`min()`、`sorted()`和`sum()`，它们能帮助我们快速分析和处理集合数据。

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_241.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_242.png)

![](img/c4a3de00b52e1f048a6362f2ffa7a8cd_244.png)

集合是处理去重数据和进行逻辑比较的利器，熟练掌握它将为你的Python编程带来很大便利。下节课我们将通过实际编码演示来进一步巩固这些知识。