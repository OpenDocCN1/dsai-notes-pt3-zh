# 哈佛大学《CS50P Python编程入门》课程 - P8：异常处理 🛡️

![](img/3da79c5f3a811d02b8a7746b49573be0_0.png)

在本节课中，我们将学习如何在Python程序中处理异常。当程序运行时出现错误，我们可以通过异常处理机制来捕获这些错误，并尝试进行修正，从而使程序能够更健壮地运行。

## 概述

![](img/3da79c5f3a811d02b8a7746b49573be0_2.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_3.png)

我们将通过一个名为 `distances.py` 的程序来学习异常处理。这个程序旨在将一个包含航天器距离（以天文单位AU为单位）的字典，转换为以米为单位并输出。我们将看到程序最初存在的一些问题，并学习如何使用 `try` 和 `except` 语句来优雅地处理这些错误。

![](img/3da79c5f3a811d02b8a7746b49573be0_4.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_5.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_6.png)

## 初始程序的问题

![](img/3da79c5f3a811d02b8a7746b49573be0_8.png)

我们有一个程序，它定义了一个距离字典，并尝试将用户输入的航天器距离从AU转换为米。

```python
distances = {
    "Voyager 1": "163",
    "Pioneer 10": "80AU",
    "New Horizons": "57",
    "Voyager 2": "136",
    "Pioneer 11": "44"
}

![](img/3da79c5f3a811d02b8a7746b49573be0_10.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_11.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_12.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_13.png)

def convert(au):
    return au * 149597870700

![](img/3da79c5f3a811d02b8a7746b49573be0_14.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_15.png)

def main():
    spacecraft = input("Enter spacecraft: ")
    au = distances[spacecraft]
    meters = convert(au)
    print(f"{spacecraft} is {meters} meters away from Earth.")

if __name__ == "__main__":
    main()
```

![](img/3da79c5f3a811d02b8a7746b49573be0_17.png)

当我们运行这个程序并输入 `Voyager 1` 时，程序会崩溃并产生一个内存错误。这是因为字典中的值 `"163"` 是一个字符串，而不是数字。在 `convert` 函数中，我们试图用 `*` 运算符将一个字符串与一个巨大的数字相乘，这会导致Python重复该字符串无数次，从而耗尽内存。

## 修复类型错误

![](img/3da79c5f3a811d02b8a7746b49573be0_19.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_20.png)

为了解决这个问题，我们需要确保传递给 `convert` 函数的是一个数字。我们可以使用 `float()` 函数将字符串转换为浮点数。

以下是修改后的 `main` 函数部分：

![](img/3da79c5f3a811d02b8a7746b49573be0_22.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_23.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_24.png)

```python
def main():
    spacecraft = input("Enter spacecraft: ")
    au = float(distances[spacecraft])  # 将字符串转换为浮点数
    meters = convert(au)
    print(f"{spacecraft} is {meters} meters away from Earth.")
```

![](img/3da79c5f3a811d02b8a7746b49573be0_26.png)

现在，当我们再次输入 `Voyager 1` 时，程序能够正确计算并输出距离。

## 处理数据格式异常

然而，我们的数据仍然存在问题。例如，字典中 `Pioneer 10` 的值是 `"80AU"`，这无法被 `float()` 函数转换，因为它包含了非数字字符 `"AU"`。

如果我们尝试输入 `Pioneer 10`，程序会抛出一个 `ValueError` 异常。

![](img/3da79c5f3a811d02b8a7746b49573be0_28.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_29.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_30.png)

为了处理这种数据格式错误，我们需要引入异常处理机制。

![](img/3da79c5f3a811d02b8a7746b49573be0_32.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_33.png)

## 使用 try 和 except 处理异常

Python 提供了 `try` 和 `except` 语句来捕获和处理异常。其基本思想是：尝试执行一段可能出错的代码，如果发生异常，则执行另一段处理异常的代码。

![](img/3da79c5f3a811d02b8a7746b49573be0_35.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_36.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_37.png)

我们可以修改 `main` 函数来捕获 `ValueError`：

![](img/3da79c5f3a811d02b8a7746b49573be0_39.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_40.png)

```python
def main():
    spacecraft = input("Enter spacecraft: ")
    try:
        au = float(distances[spacecraft])
        meters = convert(au)
        print(f"{spacecraft} is {meters} meters away from Earth.")
    except ValueError:
        print(f"Can't convert '{distances[spacecraft]}' to a float.")
        return
```

![](img/3da79c5f3a811d02b8a7746b49573be0_42.png)

现在，当用户输入 `Pioneer 10` 时，程序不会崩溃，而是会打印一条友好的错误信息并优雅地退出。

## 处理多种类型的异常

![](img/3da79c5f3a811d02b8a7746b49573be0_44.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_45.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_46.png)

上一节我们介绍了如何处理 `ValueError`。本节中我们来看看，同一行代码可能引发多种异常的情况。

![](img/3da79c5f3a811d02b8a7746b49573be0_48.png)

除了数据格式问题，用户还可能输入一个不在字典中的航天器名称。这将引发一个 `KeyError` 异常。

![](img/3da79c5f3a811d02b8a7746b49573be0_50.png)

因此，我们需要同时处理 `ValueError` 和 `KeyError`。我们可以为每种异常类型编写单独的 `except` 块。

![](img/3da79c5f3a811d02b8a7746b49573be0_52.png)

以下是更新后的 `main` 函数：

![](img/3da79c5f3a811d02b8a7746b49573be0_53.png)

```python
def main():
    spacecraft = input("Enter spacecraft: ")
    try:
        au = float(distances[spacecraft])
        meters = convert(au)
        print(f"{spacecraft} is {meters} meters away from Earth.")
    except ValueError:
        print(f"Can't convert '{distances[spacecraft]}' to a float.")
        return
    except KeyError:
        print(f"'{spacecraft}' is not in the dictionary.")
        return
```

现在，程序可以分别处理两种不同的错误情况：
*   输入 `Pioneer 10` 会触发 `ValueError`，提示无法转换。
*   输入一个不存在的名称（如 `James Webb Space Telescope`）会触发 `KeyError`，提示不在字典中。

## 最佳实践

![](img/3da79c5f3a811d02b8a7746b49573be0_55.png)

在编写异常处理代码时，遵循以下最佳实践很重要：

*   **具体化异常类型**：尽量捕获具体的异常（如 `ValueError`, `KeyError`），而不是使用通用的 `except Exception`。这有助于更清晰地了解可能发生的错误类型，并编写更有针对性的处理代码。
*   **预见异常**：在编写代码时，尝试预见可能发生的异常，并提前规划如何处理它们。

## 总结

![](img/3da79c5f3a811d02b8a7746b49573be0_57.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_59.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_60.png)

本节课中我们一起学习了Python的异常处理。我们了解到，当程序运行出错时，可以使用 `try` 和 `except` 语句来捕获并处理异常，从而避免程序崩溃，并向用户提供更友好的反馈。我们通过一个具体的例子，实践了如何处理 `ValueError` 和 `KeyError` 这两种常见异常，并了解了编写健壮代码的最佳实践。掌握异常处理是编写可靠Python程序的关键一步。