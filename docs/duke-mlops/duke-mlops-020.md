# 20：函数的使用 🧮

在本节课中，我们将学习函数的使用。我们将了解如何编写函数，如何要求函数必须接收某些参数，以及如何让函数变得更加灵活，以适应不同数量的参数需求。

## 概述

上一节我们介绍了Python的基础概念。本节中，我们将深入探讨函数。函数是组织代码、实现代码复用的核心工具。理解如何定义和使用函数，是编写高效、清晰程序的关键。

## 函数的定义与基本使用

![](img/1e3225dcd5a78f772468e2845e1b2e9d_0.png)

函数通过 `def` 关键字定义。一个基本的函数包含函数名、参数列表和函数体。

以下是定义一个简单函数的语法：

![](img/1e3225dcd5a78f772468e2845e1b2e9d_2.png)

```python
def function_name(parameters):
    # 函数体
    # 执行的操作
    return value  # 可选
```

例如，定义一个打印问候语的函数：

```python
def greet(name):
    print(f"Hello, {name}!")

# 调用函数
greet("Alice")
```

## 必需参数与默认参数

函数可以定义必需参数，调用时必须提供。也可以为参数指定默认值，使其成为可选参数。

以下是定义默认参数的示例：

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

# 调用时只提供必需参数
greet("Bob")  # 输出: Hello, Bob!

# 调用时提供所有参数
greet("Charlie", "Hi")  # 输出: Hi, Charlie!
```

## 可变长度参数

有时，我们无法预知函数需要接收多少个参数。Python提供了两种处理可变长度参数的方法：`*args` 用于接收任意数量的非关键字参数，`**kwargs` 用于接收任意数量的关键字参数。

以下是使用 `*args` 的示例：

```python
def sum_all(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

result = sum_all(1, 2, 3, 4, 5)
print(result)  # 输出: 15
```

以下是使用 `**kwargs` 的示例：

```python
def print_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

print_info(name="Diana", age=30, city="New York")
```

## 何时使用不同类型的参数

理解不同参数类型的适用场景至关重要。

以下是选择参数类型的一些指导原则：

*   **必需参数**：当函数的逻辑必须依赖某个输入值时使用。
*   **默认参数**：当某个参数有常用的默认值，但用户可能需要覆盖它时使用。
*   **`*args`**：当函数需要处理数量不确定的位置参数时使用。
*   **`**kwargs`**：当函数需要处理数量不确定的关键字参数，或者需要将参数传递给另一个函数时使用。

![](img/1e3225dcd5a78f772468e2845e1b2e9d_4.png)

## 总结

本节课中，我们一起学习了Python函数的核心用法。我们掌握了如何定义函数，如何使用必需参数和默认参数来平衡灵活性与约束，以及如何利用 `*args` 和 `**kwargs` 来处理可变数量的参数。熟练运用这些技巧，将使你能够编写出更通用、更强大的代码模块。