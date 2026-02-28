# Python编程实践：29：复合布尔表达式 🧠

![](img/dc7e0571b319d2d7ff777073bda82aa8_0.png)

在本节课中，我们将要学习如何组合简单的布尔表达式，以创建更复杂的逻辑判断。我们将重点介绍三种逻辑运算符：`and`、`or` 和 `not`，并通过具体的例子来理解它们的工作原理。

## 概述：理解复合条件

到目前为止，我们已经接触了一些布尔表达式。本节中，我们将看看如何以不同的方式组合它们，形成复合布尔表达式。复合表达式允许我们同时检查多个条件，这在编程中非常有用。

## 使用 `and` 运算符

假设你需要判断一个数字是否为自然数。我们定义自然数为任何正整数。这意味着该数字必须同时满足两个条件：是正数 **并且** 是整数。

以下是判断一个数字是否为自然数的逻辑步骤：

1.  检查数字是否大于零（正数）。
2.  检查数字的数据类型是否为整数。
3.  只有当**两个条件都为真**时，该数字才是自然数。

让我们通过一个代码示例来理解：

```python
num = 10
is_positive = num > 0
is_int = type(num) == type(5)
is_natural = is_positive and is_int
```

在这个例子中：
*   `is_positive` 的值为 `True`，因为 10 > 0。
*   `is_int` 的值为 `True`，因为 `type(10)` 和 `type(5)` 都是整数类型。
*   由于 `is_positive` 和 `is_int` 都为 `True`，所以 `is_natural = True and True` 的结果是 `True`。

`and` 运算符要求其两边的表达式都为真，整个复合表达式才为真。

## 使用 `or` 运算符

现在考虑另一个场景：决定是否穿外套。如果天气冷 **或者** 正在下雨，你就会穿外套。这里，只需要**至少一个条件为真**即可。

以下是相关的逻辑判断：

1.  检查天气是否冷。
2.  检查是否正在下雨。
3.  如果**任一条件为真**，就穿外套。

让我们看看代码实现：

```python
temp = "cold"
weather = "sunny"
is_cold = (temp == "cold")
is_raining = (weather == "raining")
wear_coat = is_cold or is_raining
```

在这个例子中：
*   `is_cold` 的值为 `True`。
*   `is_raining` 的值为 `False`。
*   由于 `is_cold` 为 `True`，所以 `wear_coat = True or False` 的结果是 `True`。你仍然需要穿外套。

`or` 运算符只要其两边的表达式有一个为真，整个复合表达式就为真。

## 逻辑运算符真值表

为了更系统地理解 `and` 和 `or`，我们可以参考下面的真值表。假设 `A` 和 `B` 代表两个任意的布尔表达式。

| A | B | A **and** B | A **or** B |
| :--- | :--- | :--- | :--- |
| False | False | False | False |
| False | True | False | True |
| True | False | False | True |
| True | True | True | True |

**核心规则总结：**
*   **`A and B`**：仅当 `A` **和** `B` 都为 `True` 时，结果为 `True`。
*   **`A or B`**：仅当 `A` **和** `B` 都为 `False` 时，结果为 `False`。只要有一个为 `True`，结果就是 `True`。

## 使用 `not` 运算符

除了组合条件，我们有时还需要反转一个条件的逻辑值。这时就需要 `not` 运算符。

`not` 运算符会取反其后布尔表达式的值：
*   如果表达式为 `True`，`not` 使其变为 `False`。
*   如果表达式为 `False`，`not` 使其变为 `True`。

请看示例：

```python
variable = 10 > 5  # 结果为 True
reverse_var = not variable  # not True 的结果是 False
```

这里，因为 `10 > 5` 是 `True`，所以 `not variable` 的结果是 `False`。

## 总结与挑战

本节课我们一起学习了如何使用三种逻辑运算符来构建复合布尔表达式：
*   **`and`**：用于检查所有条件是否同时成立。
*   **`or`**：用于检查至少一个条件是否成立。
*   **`not`**：用于反转一个条件的真假值。

![](img/dc7e0571b319d2d7ff777073bda82aa8_2.png)

![](img/dc7e0571b319d2d7ff777073bda82aa8_3.png)

掌握这些运算符是编写复杂程序逻辑的基础。给你的挑战是：思考如何在你自己的编程项目中使用复合布尔表达式。只有通过不断练习，你才能更快速、更直观地理解和运用这些概念。