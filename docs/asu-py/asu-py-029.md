# 29：字典的创建与使用 📚






在本节课中，我们将学习Python中一个非常重要的数据结构——**字典**。我们将从字典的基本概念讲起，学习如何创建和初始化字典，然后探讨如何操作字典中的数据，最后还会学习如何将列表转换为字典。





---





## 什么是字典？ 🔍





字典是一种基于**关联**而非**位置**来组织信息的数据结构。例如，当你在字典书中查找“哺乳动物”的定义时，你不会从第一页开始翻，而是直接找到“M”开头的部分，然后开始查找。Python中的字典将一组**键**与**数据值**关联起来。





可以将字典理解为一个由**键值对**组成的无序集合，其核心要求是**键必须是唯一的**。键可以是任何**不可变**的数据类型（如字符串、数字、元组），而值可以是任何数据类型。




其基本结构可以用以下代码表示：
```python
my_dict = {key1: value1, key2: value2}
```





---





## 创建与初始化字典 🛠️





上一节我们介绍了字典的概念，本节中我们来看看如何创建字典。创建字典主要有以下几种方式。




### 创建空字典
你可以创建一个空的字典，稍后再向其中添加数据。
```python
dictionary1 = {}
print(dictionary1)  # 输出: {}
```





### 直接定义键值对
在创建字典时，可以直接指定键和对应的值。
```python
dictionary1 = {'first_name': 'Sam', 'last_name': 'Simpson'}
print(dictionary1)  # 输出: {'first_name': 'Sam', 'last_name': 'Simpson'}
```





### 从列表转换
如果你有一个包含键值对元组的列表，可以轻松地将其转换为字典。
以下是转换过程的示例：
```python
# 这是一个包含（姓名，账户余额）元组的列表
accounts = [('Bob', 100), ('Sam', 200), ('Tina', 150), ('Lisa', 300)]
# 使用 dict() 函数将列表转换为字典
dictionary2 = dict(accounts)
print(dictionary2)  # 输出: {'Bob': 100, 'Sam': 200, 'Tina': 150, 'Lisa': 300}
```





### 合并两个列表为字典
有时，你的键和值可能分别存储在两个独立的列表中。以下是将其合并为一个字典的两种方法。





**方法一：使用 `for` 循环**



```python
names = ['Bob', 'Sam', 'Tina', 'Tammy']
degrees = ['Computer Science', 'Electrical Engineering', 'Biomedical Engineering', 'Mechanical Engineering']
dictionary3 = {}
for i in range(len(names)):
    dictionary3[names[i]] = degrees[i]
print(dictionary3)
```





**方法二：使用 `zip` 函数（更简洁）**
```python
dictionary3 = dict(zip(names, degrees))
print(dictionary3)
# 输出: {'Bob': 'Computer Science', 'Sam': 'Electrical Engineering', ...}
```





---





## 操作字典数据 ✏️



现在我们已经知道如何创建字典了，接下来学习如何访问、更新和删除字典中的数据。




### 访问值
要访问字典中的值，你需要使用对应的**键**。
```python
dictionary1 = {'first_name': 'Sam', 'last_name': 'Simpson'}
print(dictionary1['first_name'])  # 输出: Sam
print(dictionary1['last_name'])   # 输出: Simpson
```






### 添加或更新键值对
向字典中添加新元素或修改现有元素的值非常简单。





```python
# 添加新的键值对
dictionary1['age'] = 23
print(dictionary1)  # 输出包含 age: 23
# 更新已存在的键的值
dictionary1['age'] = 19  # 将年龄从23更正为19
print(dictionary1)
```




### 删除元素
你可以删除字典中特定的键值对，甚至清空或删除整个字典。
以下是删除操作的几种方式：
*   **删除特定键值对**：使用 `del` 语句。
    ```python
    del dictionary1['age']
    ```
*   **清空字典（保留结构）**：使用 `.clear()` 方法。
    ```python
    dictionary1.clear()  # 字典变为 {}
    ```
*   **删除整个字典**：使用 `del` 语句删除字典变量本身。
    ```python
    del dictionary1
    # 此后再次打印 dictionary1 会导致 NameError
    ```





---



## 字典的常用方法与函数 📋





除了基本操作，字典还提供了许多有用的内置方法。





以下是部分常用方法及其功能的简要说明：
*   **`len(dict)`**：返回字典中键值对的数量。
*   **`str(dict)`**：返回字典的可打印字符串表示形式。
*   **`type(dict)`**：返回对象的类型。
*   **`dict.clear()`**：移除字典中的所有元素。
*   **`dict.get(key)`**：返回指定键的值，若键不存在则返回 `None`。
*   **`dict.items()`**：返回一个包含所有（键，值）元组的列表。
*   **`dict.keys()`**：返回一个包含所有键的列表。
*   **`dict.values()`**：返回一个包含所有值的列表。
*   **`dict.update(other_dict)`**：用另一个字典的键值对更新当前字典。
*   **`dict.setdefault(key, default)`**：如果键存在则返回值，否则插入键并设置默认值。




---





## 何时使用字典？ 🤔



字典在以下场景中非常有用：
*   当你需要通过一个唯一的标识符（键）来快速查找、访问或修改数据时。
*   当数据的存储顺序不重要时。
*   当你需要频繁地添加或删除数据元素时。

反之，如果你需要维护一个有序的元素集合，那么**列表**可能是更合适的选择。

---

## 总结 📝





本节课中我们一起学习了Python字典的核心知识。我们了解了字典是一种基于键值对关联的数据结构，掌握了创建字典的多种方法，包括直接定义、从列表转换和合并列表。我们还深入练习了如何访问、更新和删除字典中的数据，并介绍了一些常用的字典方法。



![](img/15469a17a96dec6561027007374299d7_194.png)

记住，字典是处理非顺序性、需要通过唯一键快速访问数据的强大工具。在下一节课中，我们将通过实际演示来进一步巩固对字典的操作。