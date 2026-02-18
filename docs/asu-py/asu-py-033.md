# 33：异常处理 🛡️

![](img/d901016903a1bbb0caeb320d9a3167f1_0.png)

在本节课中，我们将学习Python中的异常处理。异常处理是编写健壮程序的关键，它能防止程序因意外错误而崩溃。我们将通过几个常见场景，学习如何使用 `try...except` 语句来捕获和处理错误。

![](img/d901016903a1bbb0caeb320d9a3167f1_2.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_3.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_4.png)

## 概述

![](img/d901016903a1bbb0caeb320d9a3167f1_6.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_7.png)

程序在运行过程中可能会遇到各种意外情况，例如除以零、文件不存在等。如果不处理这些错误，程序会直接崩溃。异常处理机制允许我们“捕获”这些错误，并决定程序如何优雅地应对，从而提升用户体验和程序稳定性。

![](img/d901016903a1bbb0caeb320d9a3167f1_8.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_10.png)

上一节我们介绍了文件的基本读写操作，本节中我们来看看如何在文件操作及其他场景中处理可能发生的错误。

![](img/d901016903a1bbb0caeb320d9a3167f1_12.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_14.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_16.png)

## 使用 try...except 处理除零错误

![](img/d901016903a1bbb0caeb320d9a3167f1_18.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_20.png)

最常见的错误之一是“除零错误”。当用户输入数据，而分母恰好为零时，程序通常会崩溃。

![](img/d901016903a1bbb0caeb320d9a3167f1_22.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_23.png)

为了避免这种情况，我们可以使用 `try...except` 语句。

![](img/d901016903a1bbb0caeb320d9a3167f1_25.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_26.png)

以下是一个示例代码：

![](img/d901016903a1bbb0caeb320d9a3167f1_28.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_30.png)

```python
try:
    print(14 / 0)
except ZeroDivisionError:
    print("不能除以零。")
```

![](img/d901016903a1bbb0caeb320d9a3167f1_32.png)

如果不使用异常处理，直接运行 `print(14 / 0)`，程序会崩溃并显示 `ZeroDivisionError: division by zero`。

![](img/d901016903a1bbb0caeb320d9a3167f1_33.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_35.png)

使用 `try...except` 后，程序会捕获这个错误，并执行 `except` 块中的代码，打印出自定义的错误信息“不能除以零。”，然后程序会继续正常退出，而不会崩溃。

![](img/d901016903a1bbb0caeb320d9a3167f1_37.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_38.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_40.png)

## 处理文件操作中的异常

![](img/d901016903a1bbb0caeb320d9a3167f1_42.png)

另一个需要使用异常处理的常见场景是文件操作。例如，尝试打开一个不存在的文件会导致程序崩溃。

![](img/d901016903a1bbb0caeb320d9a3167f1_43.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_45.png)

以下是处理文件读取错误的示例：

![](img/d901016903a1bbb0caeb320d9a3167f1_46.png)

```python
try:
    file = open('不存在的文件.txt', 'r')
except IOError as e:
    print(f"发生错误：{e}")
```

![](img/d901016903a1bbb0caeb320d9a3167f1_48.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_49.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_51.png)

运行这段代码，如果文件不存在，程序不会崩溃，而是会捕获 `IOError` 并打印出类似“发生错误：[Errno 2] No such file or directory: ‘不存在的文件.txt’”的信息。

![](img/d901016903a1bbb0caeb320d9a3167f1_53.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_54.png)

接下来，我们看看文件写入的例子。

![](img/d901016903a1bbb0caeb320d9a3167f1_56.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_58.png)

以下是处理文件写入的示例：

![](img/d901016903a1bbb0caeb320d9a3167f1_60.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_62.png)

```python
try:
    file = open('新文件.txt', 'w')
    file.write('欢迎来到Python。')
except IOError as e:
    print(f"发生错误：{e}")
finally:
    print("正在关闭文件。")
    file.close()
```

![](img/d901016903a1bbb0caeb320d9a3167f1_64.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_66.png)

在这个例子中，我们尝试写入一个新文件。`finally` 块中的代码无论 `try` 块中的操作成功还是失败都会执行，通常用于执行清理工作，比如确保文件被关闭。

![](img/d901016903a1bbb0caeb320d9a3167f1_68.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_69.png)

运行这段代码，它会创建“新文件.txt”并写入内容，最后打印“正在关闭文件。”。

![](img/d901016903a1bbb0caeb320d9a3167f1_71.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_72.png)

## 处理多种类型的异常

![](img/d901016903a1bbb0caeb320d9a3167f1_74.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_75.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_77.png)

有时，一段代码可能引发多种不同类型的异常。我们可以使用一个通用的 `except` 块来捕获所有异常，并通过 `sys.exc_info()` 获取错误信息。

![](img/d901016903a1bbb0caeb320d9a3167f1_79.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_80.png)

以下是一个遍历列表并计算倒数的例子，列表中包含可能引发错误的不同数据类型：

![](img/d901016903a1bbb0caeb320d9a3167f1_82.png)

```python
import sys

![](img/d901016903a1bbb0caeb320d9a3167f1_84.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_86.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_87.png)

my_list = [‘a‘, 0, 2]

![](img/d901016903a1bbb0caeb320d9a3167f1_89.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_90.png)

for item in my_list:
    try:
        print(f"当前项是：{item}")
        reciprocal = 1 / item
        print(f"{item} 的倒数是 {reciprocal}")
    except:
        error_type, error_value, _ = sys.exc_info()
        print(f"哎呀，发生了 {error_type.__name__}：{error_value}")
```

![](img/d901016903a1bbb0caeb320d9a3167f1_92.png)

运行这段代码，输出如下：
- 对于 `‘a‘`：会捕获 `ValueError`，因为字符串不能参与除法。
- 对于 `0`：会捕获 `ZeroDivisionError`，因为不能除以零。
- 对于 `2`：计算成功，打印出倒数 0.5。

![](img/d901016903a1bbb0caeb320d9a3167f1_93.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_95.png)

这个例子展示了如何让程序在遇到部分错误时继续运行，并完成剩余的任务。

![](img/d901016903a1bbb0caeb320d9a3167f1_97.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_98.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_100.png)

## 总结

![](img/d901016903a1bbb0caeb320d9a3167f1_102.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_103.png)

本节课中我们一起学习了Python异常处理的核心概念。我们了解到：
1.  **`try...except` 语句**是处理错误的基本结构。
2.  使用异常处理可以防止程序意外崩溃，提升健壮性。
3.  在文件操作等I/O场景中，异常处理尤为重要。
4.  **`finally` 块**用于确保无论是否发生异常，某些清理代码（如关闭文件）都会执行。
5.  可以使用 `sys.exc_info()` 来获取未明确指定类型的异常信息。

![](img/d901016903a1bbb0caeb320d9a3167f1_105.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_106.png)

通过合理使用异常处理，你可以编写出更稳定、更友好的Python应用程序。