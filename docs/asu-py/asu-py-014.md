# 14：Python 算术表达式 🧮

![](img/54f2c3b39e35705ff95edcaa7aedebf2_1.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_2.png)

在本节课中，我们将学习 Python 中的算术表达式。我们将了解什么是算术表达式，学习 Python 的运算顺序规则，并通过几个演示来理解如何编写算术表达式。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_4.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_6.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_7.png)

## 什么是算术表达式？ ➕➖✖️➗

![](img/54f2c3b39e35705ff95edcaa7aedebf2_9.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_10.png)

算术表达式是数学的一个分支，涉及对数字和数值运算的研究。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_12.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_14.png)

在 Python 中，算术运算符包括以下几种：

![](img/54f2c3b39e35705ff95edcaa7aedebf2_16.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_17.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_18.png)

以下是 Python 中的主要算术运算符：

![](img/54f2c3b39e35705ff95edcaa7aedebf2_20.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_21.png)

*   **加法**：`+`
*   **减法**：`-`
*   **乘法**：`*`
*   **除法**：`/`
*   **取模（求余）**：`%`
*   **幂运算**：`**`
*   **整除（向下取整除法）**：`//`

![](img/54f2c3b39e35705ff95edcaa7aedebf2_22.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_24.png)

## 运算顺序（PEMDAS） 📝

![](img/54f2c3b39e35705ff95edcaa7aedebf2_25.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_27.png)

上一节我们介绍了 Python 中的基本算术运算符，本节中我们来看看 Python 如何决定这些运算符的执行顺序。Python 遵循的运算顺序规则被称为 **PEMDAS**。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_29.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_31.png)

PEMDAS 代表：
1.  **P**arentheses - 括号
2.  **E**xponentiation - 幂运算
3.  **M**ultiplication - 乘法
4.  **D**ivision - 除法
5.  **A**ddition - 加法
6.  **S**ubtraction - 减法

![](img/54f2c3b39e35705ff95edcaa7aedebf2_32.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_34.png)

需要注意的是，乘法、除法、取模和整除具有相同的优先级，按从左到右的顺序执行。加法和减法也具有相同的优先级，同样按从左到右的顺序执行。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_36.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_37.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_38.png)

此外，在 Python 3 中，除法运算符 `/` 总是返回一个浮点数。如果想进行整数除法并得到一个整数结果，需要使用整除运算符 `//`。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_40.png)

## 演示：编写算术表达式 💻

![](img/54f2c3b39e35705ff95edcaa7aedebf2_41.png)

现在，让我们通过几个演示来具体看看如何在 Python 中编写和使用算术表达式。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_43.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_44.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_45.png)

### 示例 1：直接使用数值

![](img/54f2c3b39e35705ff95edcaa7aedebf2_47.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_48.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_50.png)

在第一个示例中，我们直接使用数值创建了几个变量来执行不同的算术运算。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_51.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_52.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_54.png)

以下是变量定义和运算：

![](img/54f2c3b39e35705ff95edcaa7aedebf2_56.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_57.png)

```python
sum = 2 + 2
difference = 9123421 - 1305
product = 2 * 2
quotient = 4 / 2
remainder = 5 % 2
exponential = 2 ** 3
floor_division = 5 // 2
```

运行这些代码后，打印每个变量的值，我们可以看到相应的计算结果，例如 `sum` 是 4，`difference` 是 9122116。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_59.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_60.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_61.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_62.png)

### 示例 2：使用变量存储数值

![](img/54f2c3b39e35705ff95edcaa7aedebf2_64.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_65.png)

第二个示例展示了使用变量来存储数值，再进行运算，这种方法更加高效。

以下是使用变量的示例：

![](img/54f2c3b39e35705ff95edcaa7aedebf2_67.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_68.png)

```python
num1 = 200
num2 = 10

![](img/54f2c3b39e35705ff95edcaa7aedebf2_69.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_70.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_71.png)

sum = num1 + num2
difference = num1 - num2
product = num1 * num2
quotient = num1 / num2
remainder = num1 % num2
exponential = num1 ** num2
floor_division = num1 // num2
```

这种方法的好处是，如果需要修改参与运算的数值，只需更改变量 `num1` 和 `num2` 的值，所有相关的计算结果都会自动更新，无需逐一修改每个表达式中的数字。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_73.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_74.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_75.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_76.png)

### 示例 3：运算顺序的应用

接下来，我们通过一个例子来理解 PEMDAS 规则的实际应用。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_78.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_79.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_80.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_81.png)

首先是一个简单例子：`(14 - 7) / 7`。根据 PEMDAS，括号内的运算 `14 - 7` 优先执行，得到 7，然后执行除法 `7 / 7`，最终结果为 `1.0`。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_83.png)

然后是一个更复杂的表达式：`((((18 + 2) * 2) - 8) // 2) - (4 * 2)`。我们按照 PEMDAS 规则逐步拆解：
1.  最内层括号：`18 + 2 = 20`
2.  下一层：`20 * 2 = 40`
3.  再下一层：`40 - 8 = 32`
4.  接着：`32 // 2 = 16`
5.  计算右侧乘法：`4 * 2 = 8`
6.  最后执行减法：`16 - 8 = 8`

![](img/54f2c3b39e35705ff95edcaa7aedebf2_84.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_86.png)

因此，整个表达式的结果是 `8`。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_87.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_89.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_90.png)

### 示例 4：直接打印表达式结果

![](img/54f2c3b39e35705ff95edcaa7aedebf2_92.png)

最后，我们也可以不将结果赋值给变量，而是直接在 `print` 语句中使用算术表达式。例如，`print(4 / 2)` 会直接输出结果 `2.0`。

![](img/54f2c3b39e35705ff95edcaa7aedebf2_93.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_94.png)

## 总结 🎯

![](img/54f2c3b39e35705ff95edcaa7aedebf2_96.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_97.png)

![](img/54f2c3b39e35705ff95edcaa7aedebf2_99.png)

本节课中我们一起学习了 Python 的算术表达式。我们首先认识了加法、减法、乘法、除法等基本算术运算符。然后，我们深入了解了 Python 遵循的运算顺序规则 PEMDAS，它决定了表达式中各部分的计算顺序。最后，我们通过多个演示，练习了如何编写算术表达式，包括直接使用数值、利用变量提高效率，以及应用 PEMDAS 规则来解析复杂表达式。掌握这些内容是进行更复杂 Python 编程的基础。