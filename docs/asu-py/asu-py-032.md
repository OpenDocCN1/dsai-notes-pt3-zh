# 32：Python 文件写入与重命名操作 🖋️📁

![](img/c028db28d3f5b2504af7451bd64b01b2_0.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_2.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_3.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_4.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_5.png)

在本节课中，我们将学习如何使用 Python 进行文件操作，具体包括将文件内容写入一个新文件，以及如何重命名一个文件。我们将使用 `open()` 函数的不同模式，并借助 `os` 模块来完成这些任务。

![](img/c028db28d3f5b2504af7451bd64b01b2_7.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_8.png)

---

![](img/c028db28d3f5b2504af7451bd64b01b2_10.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_12.png)

## 第一部分：将文件内容写入新文件

![](img/c028db28d3f5b2504af7451bd64b01b2_14.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_16.png)

上一节我们介绍了文件读取的基础知识，本节中我们来看看如何将读取到的内容写入到一个全新的文件中。

![](img/c028db28d3f5b2504af7451bd64b01b2_18.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_19.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_21.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_23.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_24.png)

首先，我们需要打开一个已存在的文件并读取其内容。以下是实现此功能的核心步骤：

![](img/c028db28d3f5b2504af7451bd64b01b2_26.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_28.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_29.png)

1.  **打开源文件**：使用 `open()` 函数以读取模式打开文件。
2.  **读取内容**：使用 `.read()` 方法将文件内容读取到一个变量中。
3.  **创建并写入新文件**：使用 `open()` 函数以写入模式创建一个新文件，并使用 `.write()` 方法将内容写入。
4.  **验证结果**：重新打开新创建的文件，读取并打印其内容以验证写入操作成功。

![](img/c028db28d3f5b2504af7451bd64b01b2_30.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_32.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_34.png)

以下是实现上述步骤的代码示例：

![](img/c028db28d3f5b2504af7451bd64b01b2_36.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_38.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_40.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_41.png)

```python
# 1. 打开源文件并读取内容
f = open(r‘你的文件路径\MobyDick.txt‘, ‘r‘)
file_text = f.read()
print("这是《白鲸记》第一章的节选：")
print(file_text)

![](img/c028db28d3f5b2504af7451bd64b01b2_43.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_45.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_47.png)

# 2. 创建新文件并写入内容
f_write = open(‘updated_text.txt‘, ‘w‘)
f_write.write(file_text)
f_write.close()

![](img/c028db28d3f5b2504af7451bd64b01b2_49.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_50.png)

# 3. 验证新文件内容
f_updated = open(‘updated_text.txt‘, ‘r‘)
updated_data = f_updated.read()
print("\n来自新文件的数据：")
print(updated_data)
f_updated.close()
```

![](img/c028db28d3f5b2504af7451bd64b01b2_52.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_54.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_56.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_58.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_59.png)

运行这段代码后，你会在当前目录下看到一个名为 `updated_text.txt` 的新文件，其内容与源文件 `MobyDick.txt` 完全一致。

![](img/c028db28d3f5b2504af7451bd64b01b2_60.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_62.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_64.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_65.png)

---

![](img/c028db28d3f5b2504af7451bd64b01b2_67.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_68.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_69.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_70.png)

## 第二部分：重命名文件

![](img/c028db28d3f5b2504af7451bd64b01b2_72.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_74.png)

完成了文件写入操作后，接下来我们学习一个更复杂的任务：重命名文件。这需要借助 Python 的 `os` 模块。

以下是重命名文件的核心步骤：

![](img/c028db28d3f5b2504af7451bd64b01b2_76.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_78.png)

1.  **导入 os 模块**：`os` 模块提供了与操作系统交互的功能。
2.  **备份原文件内容**：打开原文件，读取内容并保存到变量中，然后关闭文件。
3.  **创建临时新文件**：将备份的内容写入一个临时的新文件中。
4.  **删除原文件**：使用 `os.remove()` 函数删除原文件。
5.  **重命名临时文件**：使用 `os.rename()` 函数将临时文件重命名为我们想要的新名字。

![](img/c028db28d3f5b2504af7451bd64b01b2_79.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_80.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_82.png)

以下是实现文件重命名的代码示例：

![](img/c028db28d3f5b2504af7451bd64b01b2_84.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_85.png)

```python
import os

![](img/c028db28d3f5b2504af7451bd64b01b2_87.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_88.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_90.png)

# 1. 读取原文件内容并备份
f = open(r‘你的文件路径\MobyDick.txt‘, ‘r‘)
file_text = f.read()
f.close()

![](img/c028db28d3f5b2504af7451bd64b01b2_92.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_94.png)

# 2. 将内容写入一个临时新文件
f_new = open(‘new_file.txt‘, ‘w‘)
f_new.write(file_text)
f_new.close()

![](img/c028db28d3f5b2504af7451bd64b01b2_96.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_98.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_100.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_101.png)

# 3. 删除原文件
os.remove(‘MobyDick.txt‘)

![](img/c028db28d3f5b2504af7451bd64b01b2_103.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_104.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_106.png)

# 4. 将临时文件重命名为新名称
os.rename(‘new_file.txt‘, ‘MobyDick1.txt‘)
```

![](img/c028db28d3f5b2504af7451bd64b01b2_108.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_109.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_110.png)

执行这段代码后，原文件 `MobyDick.txt` 会被删除，而其内容会被保存在新命名的文件 `MobyDick1.txt` 中。通过检查文件夹，你可以确认这一变化。

![](img/c028db28d3f5b2504af7451bd64b01b2_112.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_114.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_116.png)

---

![](img/c028db28d3f5b2504af7451bd64b01b2_118.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_120.png)

## 总结

![](img/c028db28d3f5b2504af7451bd64b01b2_122.png)

![](img/c028db28d3f5b2504af7451bd64b01b2_124.png)

本节课中我们一起学习了两个重要的文件操作：
1.  **文件写入**：我们掌握了如何使用 `open()` 函数的 `‘w‘` 模式创建新文件，并使用 `.write()` 方法将数据写入其中。
2.  **文件重命名**：我们学习了如何结合 `os` 模块的 `remove()` 和 `rename()` 函数，通过“读取-备份-删除-重命名”的流程来安全地重命名一个文件。

![](img/c028db28d3f5b2504af7451bd64b01b2_126.png)

这些操作是处理数据和文件管理的基础，熟练掌握它们将为你的编程工作带来很大便利。