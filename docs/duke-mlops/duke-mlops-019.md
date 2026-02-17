# 19：19_01_06_课程回顾-数据添加与提取 📚

在本节课中，我们将回顾如何向Python的两种核心数据结构——列表（List）和字典（Dictionary）——添加数据，以及从它们中提取数据。掌握这些操作是高效处理数据的基础。

## 向数据结构添加数据 ➕

上一节我们介绍了列表和字典的基本概念，本节中我们来看看如何向它们添加新的元素。

![](img/b866f270c832d68f8d4e36dce0631376_0.png)

### 向列表添加数据

![](img/b866f270c832d68f8d4e36dce0631376_2.png)

列表是一种有序的集合。以下是向列表添加数据的几种主要方法：

*   **使用 `append()` 方法**：在列表**末尾**添加一个元素。
    ```python
    my_list = [1, 2, 3]
    my_list.append(4)
    # 结果：my_list 变为 [1, 2, 3, 4]
    ```
*   **使用 `insert()` 方法**：在列表的**指定索引位置**插入一个元素。
    ```python
    my_list = [1, 2, 3]
    my_list.insert(1, 'a')
    # 结果：my_list 变为 [1, 'a', 2, 3]
    ```
*   **使用 `extend()` 方法或 `+` 运算符**：将另一个列表的所有元素添加到当前列表末尾。
    ```python
    my_list = [1, 2, 3]
    my_list.extend([4, 5])
    # 或 my_list = my_list + [4, 5]
    # 结果：my_list 变为 [1, 2, 3, 4, 5]
    ```

### 向字典添加数据

字典是一种键值对（Key-Value Pair）的集合。以下是向字典添加数据的方法：

*   **直接赋值**：通过新的键（Key）直接赋值，即可添加新的键值对。
    ```python
    my_dict = {'name': 'Alice', 'age': 25}
    my_dict['city'] = 'New York'
    # 结果：my_dict 变为 {'name': 'Alice', 'age': 25, 'city': 'New York'}
    ```
*   **使用 `update()` 方法**：用另一个字典或键值对序列更新当前字典，添加或覆盖条目。
    ```python
    my_dict = {'name': 'Alice', 'age': 25}
    my_dict.update({'city': 'New York', 'age': 26})
    # 结果：my_dict 变为 {'name': 'Alice', 'age': 26, 'city': 'New York'}
    ```

## 从数据结构提取数据 📤

了解了如何添加数据后，接下来我们学习如何从这些结构中提取所需的数据。

### 从列表提取数据

列表通过索引（位置）来访问元素。以下是提取数据的方法：

*   **通过索引访问**：使用方括号 `[]` 和索引（从0开始）获取单个元素。
    ```python
    my_list = ['a', 'b', 'c', 'd']
    element = my_list[2]
    # 结果：element 的值为 'c'
    ```
*   **切片（Slicing）**：使用 `[start:end:step]` 语法获取一个子列表。
    ```python
    my_list = ['a', 'b', 'c', 'd', 'e']
    sub_list = my_list[1:4]
    # 结果：sub_list 为 ['b', 'c', 'd']
    ```

### 从字典提取数据

字典通过键（Key）来访问对应的值（Value）。以下是提取数据的方法：

*   **通过键访问值**：使用方括号 `[]` 和键名来获取对应的值。
    ```python
    my_dict = {'name': 'Alice', 'age': 25, 'city': 'New York'}
    value = my_dict['name']
    # 结果：value 的值为 'Alice'
    ```
*   **使用 `get()` 方法**：通过键获取值，如果键不存在可以返回默认值，避免程序报错。
    ```python
    my_dict = {'name': 'Alice', 'age': 25}
    value = my_dict.get('city', 'Unknown')
    # 结果：因为键‘city’不存在，value 的值为 'Unknown'
    ```
*   **获取所有键、值或键值对**：
    ```python
    my_dict = {'name': 'Alice', 'age': 25}
    keys = my_dict.keys()   # 获取所有键
    values = my_dict.values() # 获取所有值
    items = my_dict.items() # 获取所有键值对（元组形式）
    ```

## 总结 ✨

![](img/b866f270c832d68f8d4e36dce0631376_4.png)

本节课中我们一起学习了Python列表和字典的核心操作。

你现在已经掌握了如何向列表和字典添加数据，也了解了从这些数据结构中提取数据的各种方法。你能够辨别在何种情况下应使用哪种数据结构，并知晓在处理数据时，与这些数据结构进行交互和提取数据的一些高效方式。