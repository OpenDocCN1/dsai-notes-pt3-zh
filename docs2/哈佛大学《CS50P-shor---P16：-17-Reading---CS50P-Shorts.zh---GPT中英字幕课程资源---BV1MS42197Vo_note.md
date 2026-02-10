# 哈佛大学《CS50P》Python编程入门 2024 短片课程 - P16：📖 读写CSV文件

![](img/9137c940096fb5e246eed99e8fe90e73_0.png)

![](img/9137c940096fb5e246eed99e8fe90e73_2.png)

![](img/9137c940096fb5e246eed99e8fe90e73_0.png)

在本节课中，我们将要学习如何使用Python读取和写入CSV文件。CSV文件非常适合存储以逗号分隔的数据，并且结合Python，它们成为数据分析的强大工具。我们将通过一个具体的例子，分析一组艺术作品的亮度数据，并将结果写入一个新的CSV文件。

## 概述与目标

本节课的目标是编写一个程序，从一个名为 `views.csv` 的文件中读取数据。这个文件包含了36幅富士山版画的信息，每幅画都有ID、英文标题和日文标题。我们的程序将读取这些数据，计算每幅对应JPEG图片的亮度值，最后将原始数据连同计算出的亮度值一起写入一个新的 `analysis.csv` 文件。

## 第一步：读取CSV文件

![](img/9137c940096fb5e246eed99e8fe90e73_4.png)

要读取CSV文件，我们需要使用Python内置的 `csv` 库。这个库提供了方便的工具来处理CSV格式的数据。

![](img/9137c940096fb5e246eed99e8fe90e73_5.png)

以下是读取CSV文件的基本步骤：

![](img/9137c940096fb5e246eed99e8fe90e73_7.png)

![](img/9137c940096fb5e246eed99e8fe90e73_8.png)

1.  导入 `csv` 模块。
2.  使用 `with open(...)` 语句以读取模式打开文件。
3.  使用 `csv.DictReader` 创建一个阅读器对象，它将文件的每一行作为一个字典返回。

![](img/9137c940096fb5e246eed99e8fe90e73_10.png)

![](img/9137c940096fb5e246eed99e8fe90e73_11.png)

让我们看看具体的代码实现：

```python
import csv

with open(“views.csv”, “r”) as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(row)
```

![](img/9137c940096fb5e246eed99e8fe90e73_13.png)

在这段代码中：
*   `with open(“views.csv”, “r”) as file:` 这行代码打开了 `views.csv` 文件用于读取，并确保文件在使用后会自动关闭。
*   `reader = csv.DictReader(file)` 创建了一个 `DictReader` 对象。它会自动将CSV文件的第一行作为字典的键（即列名）。
*   `for row in reader:` 循环遍历文件中的每一行数据。
*   `print(row)` 打印出每一行，此时每一行都是一个字典，例如：`{‘ID’: ‘1’, ‘English title’: ‘The Great Wave off Kanagawa’, …}`。

运行这段代码，你将看到文件中的所有数据以字典列表的形式打印出来。

![](img/9137c940096fb5e246eed99e8fe90e73_15.png)

## 第二步：处理数据并计算亮度

![](img/9137c940096fb5e246eed99e8fe90e73_17.png)

![](img/9137c940096fb5e246eed99e8fe90e73_18.png)

上一节我们成功读取了CSV数据。本节中，我们来看看如何利用这些数据。我们的目标是计算每幅版画对应图片的亮度。

![](img/9137c940096fb5e246eed99e8fe90e73_20.png)

我们注意到，CSV文件中的 `ID` 列（例如1, 2, 3…）正好对应着图片的文件名（1.jpg, 2.jpg, 3.jpg…）。我们可以利用这个对应关系。

假设我们有一个函数 `calculate_brightness(filename)`，它接收一个文件名，返回一个0到1之间的亮度值（1代表最亮，0代表最暗）。

![](img/9137c940096fb5e246eed99e8fe90e73_22.png)

以下是整合计算亮度的步骤：

![](img/9137c940096fb5e246eed99e8fe90e73_24.png)

1.  在循环中，从每一行的字典中获取 `ID`。
2.  使用 `ID` 拼接出对应的JPEG文件名。
3.  调用 `calculate_brightness` 函数计算该图片的亮度。
4.  打印出亮度值。

![](img/9137c940096fb5e246eed99e8fe90e73_26.png)

```python
import csv

def calculate_brightness(filename):
    # 假设这是一个已实现的函数，用于计算图片亮度
    # 此处为示例，实际需要图像处理库（如PIL）来实现
    return 0.5  # 示例返回值

![](img/9137c940096fb5e246eed99e8fe90e73_28.png)

with open(“views.csv”, “r”) as file:
    reader = csv.DictReader(file)
    for row in reader:
        # 构建文件名，例如 “1.jpg”
        filename = f”{row[‘ID’]}.jpg”
        # 计算亮度
        brightness = calculate_brightness(filename)
        # 打印结果，保留两位小数
        print(round(brightness, 2))
```

![](img/9137c940096fb5e246eed99e8fe90e73_30.png)

![](img/9137c940096fb5e246eed99e8fe90e73_31.png)

现在，程序会为每一幅版画计算并输出其亮度值。

![](img/9137c940096fb5e246eed99e8fe90e73_33.png)

![](img/9137c940096fb5e246eed99e8fe90e73_34.png)

![](img/9137c940096fb5e246eed99e8fe90e73_35.png)

## 第三步：写入新的CSV文件

![](img/9137c940096fb5e246eed99e8fe90e73_37.png)

我们已经能够读取数据并计算新信息。接下来，我们需要将原始数据和新计算的亮度值一起保存到一个新的CSV文件中。

![](img/9137c940096fb5e246eed99e8fe90e73_39.png)

这涉及到同时打开两个文件：一个用于读取原始数据，另一个用于写入新数据。`csv` 库也提供了 `csv.DictWriter` 对象来帮助我们写入字典格式的数据。

![](img/9137c940096fb5e246eed99e8fe90e73_41.png)

以下是同时进行读写操作的步骤：

![](img/9137c940096fb5e246eed99e8fe90e73_43.png)

![](img/9137c940096fb5e246eed99e8fe90e73_44.png)

![](img/9137c940096fb5e246eed99e8fe90e73_46.png)

1.  在同一个 `with` 语句中打开两个文件。
2.  为写入文件创建一个 `DictWriter` 对象，并指定列名（字段名）。
3.  在循环中，为每一行原始数据添加新的 `brightness` 键值对。
4.  使用 `writerow()` 方法将更新后的字典写入新文件。

![](img/9137c940096fb5e246eed99e8fe90e73_47.png)

![](img/9137c940096fb5e246eed99e8fe90e73_49.png)

```python
import csv

![](img/9137c940096fb5e246eed99e8fe90e73_51.png)

![](img/9137c940096fb5e246eed99e8fe90e73_52.png)

def calculate_brightness(filename):
    return 0.5  # 示例函数

![](img/9137c940096fb5e246eed99e8fe90e73_54.png)

![](img/9137c940096fb5e246eed99e8fe90e73_56.png)

![](img/9137c940096fb5e246eed99e8fe90e73_58.png)

# 同时打开两个文件
with open(“views.csv”, “r”) as views, open(“analysis.csv”, “w”) as analysis:
    reader = csv.DictReader(views)
    # 定义新CSV文件的列名：原始列名 + 新的“brightness”列
    fieldnames = reader.fieldnames + [“brightness”]
    writer = csv.DictWriter(analysis, fieldnames=fieldnames)

    # 写入标题行
    writer.writeheader()

    for row in reader:
        filename = f”{row[‘ID’]}.jpg”
        brightness = calculate_brightness(filename)
        # 为当前行字典添加新的亮度键值对
        row[“brightness”] = round(brightness, 2)
        # 将更新后的行写入新文件
        writer.writerow(row)
```

![](img/9137c940096fb5e246eed99e8fe90e73_60.png)

在这段代码中：
*   `fieldnames = reader.fieldnames + [“brightness”]` 这行代码巧妙地获取了原始文件的列名，并添加了新的 `”brightness”` 列。
*   `row[“brightness”] = round(brightness, 2)` 直接修改了当前行的字典，添加了亮度值，这使得写入新行变得非常简单，只需 `writer.writerow(row)`。

运行此程序后，你会得到一个名为 `analysis.csv` 的新文件，它包含了所有原始信息以及新增的亮度列。

![](img/9137c940096fb5e246eed99e8fe90e73_62.png)

## 总结

本节课中我们一起学习了Python处理CSV文件的核心操作：
1.  **读取**：使用 `csv.DictReader` 可以方便地将CSV的每一行作为字典读取，键是列标题。
2.  **处理**：我们可以遍历这些字典，访问其中的数据，并进行任何需要的计算或分析。
3.  **写入**：使用 `csv.DictWriter` 可以将字典数据写回CSV文件。我们可以轻松地添加新的列（如本节课的 `brightness`），只需更新字典并写入即可。

通过 `with` 语句管理文件，以及利用 `DictReader` 和 `DictWriter` 对象，Python让CSV文件的读写变得清晰而高效。你可以将这种方法应用于各种需要数据导入、处理、导出的场景中。

![](img/9137c940096fb5e246eed99e8fe90e73_64.png)

![](img/9137c940096fb5e246eed99e8fe90e73_64.png)