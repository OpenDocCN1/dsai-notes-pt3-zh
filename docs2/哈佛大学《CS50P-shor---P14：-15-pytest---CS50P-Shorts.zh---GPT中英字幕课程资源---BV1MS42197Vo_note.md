# 哈佛大学《CS50P Python编程入门》短课程 - P14：pytest 🧪

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_0.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_2.png)

在本节课中，我们将学习如何使用 `pytest` 模块来更彻底地测试你的代码。我们将通过一个具体的例子，了解如何编写测试函数、测试不同类型的输入以及如何处理浮点数精度问题。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_4.png)

---

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_6.png)

## 概述

`pytest` 是一个用于编写和运行测试的Python模块。它可以帮助你自动验证代码是否按预期工作，比手动测试更高效、更全面。我们将通过一个将天文单位（AU）转换为米（meter）的程序来演示 `pytest` 的基本用法。

---

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_8.png)

## 示例程序：convert.py

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_10.png)

我们有一个名为 `convert.py` 的程序，其功能是将天文单位（AU）转换为米。以下是该程序的核心函数：

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_11.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_12.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_13.png)

```python
def convert(AU):
    if not isinstance(AU, (int, float)):
        raise TypeError("AU must be an int or float")
    return AU * 149597870700
```

这个函数首先检查输入 `AU` 是否为整数或浮点数。如果不是，则抛出一个 `TypeError` 异常。如果是，则返回转换后的米数。

---

## 编写测试文件

为了使用 `pytest` 测试我们的代码，我们需要创建一个测试文件。按照惯例，测试文件的名称应以 `test_` 开头。因此，我们创建一个名为 `test_convert.py` 的文件。

首先，我们需要导入 `pytest` 模块以及要测试的函数：

```python
import pytest
from convert import convert
```

---

## 测试整数转换

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_15.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_16.png)

上一节我们介绍了如何设置测试文件，本节中我们来看看如何编写第一个测试函数。我们将测试 `convert` 函数对整数输入的处理。

以下是测试整数转换的示例：

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_18.png)

```python
def test_conversion():
    assert convert(1) == 149597870700
    assert convert(50) == 7479893535000
```

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_20.png)

在这个测试函数中，我们使用 `assert` 语句来验证 `convert` 函数的输出是否等于预期值。如果断言失败，`pytest` 会报告错误。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_22.png)

运行 `pytest` 命令，我们可以看到测试是否通过。

---

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_24.png)

## 测试错误处理

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_25.png)

除了测试正常情况，我们还需要测试代码在异常情况下的行为。例如，当输入不是整数或浮点数时，`convert` 函数应该抛出 `TypeError` 异常。

以下是测试错误处理的示例：

```python
def test_error():
    with pytest.raises(TypeError):
        convert("1")
```

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_27.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_28.png)

在这个测试中，我们使用 `pytest.raises` 上下文管理器来验证 `convert` 函数在接收到字符串输入时是否会抛出 `TypeError` 异常。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_30.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_31.png)

---

## 测试浮点数转换

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_33.png)

由于浮点数在计算机中的表示存在精度问题，直接比较两个浮点数可能会失败。因此，我们需要使用近似比较来测试浮点数转换。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_35.png)

以下是测试浮点数转换的示例：

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_37.png)

```python
def test_float_conversion():
    expected = 149597870.691
    result = convert(0.001)
    assert result == pytest.approx(expected, abs=0.01)
```

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_38.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_40.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_41.png)

在这个测试中，我们使用 `pytest.approx` 来比较 `convert` 函数的输出与预期值。`abs` 参数指定了允许的绝对误差范围。

---

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_43.png)

## 调整容差

在实际应用中，我们可能需要根据需求调整容差。例如，对于高精度科学计算，我们可能需要更严格的容差；而对于一般应用，较宽松的容差可能就足够了。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_45.png)

以下是调整容差的示例：

```python
def test_float_conversion_strict():
    expected = 149597870.691
    result = convert(0.001)
    assert result == pytest.approx(expected, abs=1e-2)
```

在这个测试中，我们将容差设置为 `1e-2`（即0.01）。如果 `convert` 函数的输出与预期值的差异在这个范围内，测试就会通过。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_47.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_49.png)

---

## 总结

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_51.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_52.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_53.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_54.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_55.png)

本节课中我们一起学习了如何使用 `pytest` 模块来测试Python代码。我们介绍了如何编写测试文件、测试整数和浮点数转换、测试错误处理以及如何调整容差。通过 `pytest`，我们可以更高效、更全面地验证代码的正确性，确保程序在各种情况下都能按预期工作。