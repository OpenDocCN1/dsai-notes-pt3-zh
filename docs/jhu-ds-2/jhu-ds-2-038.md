# 038：作用域规则 🔍

![](img/e648c4e2da59bc8f1aac20de0dcb4731_0.png)

在本节课中，我们将学习R语言中一个核心概念——**作用域规则**。理解作用域规则对于编写高效、可预测的R代码至关重要。我们将探讨R如何查找变量的值，特别是当函数嵌套定义时，以及这与动态作用域的区别。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_2.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_3.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_4.png)

## 全局环境与自由变量

![](img/e648c4e2da59bc8f1aac20de0dcb4731_5.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_6.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_7.png)

上一节我们介绍了函数的基本结构，本节中我们来看看R如何解析函数中未定义的变量。

通常，函数在全局环境中定义。这意味着，如果函数内部无法找到某个变量的值（即**自由变量**），R会到用户的**全局工作空间**中查找。这是符合大多数人预期的行为。

以下是R查找自由变量的基本规则：

![](img/e648c4e2da59bc8f1aac20de0dcb4731_9.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_10.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_11.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_12.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_13.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_14.png)

*   如果变量在函数内部定义（作为参数或局部变量），则使用该值。
*   如果变量未在函数内部定义，R会到该函数被**定义时**所在的环境（即其**定义环境**）中查找。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_15.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_16.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_17.png)

## 函数嵌套与词法作用域

![](img/e648c4e2da59bc8f1aac20de0dcb4731_19.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_20.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_21.png)

R的一个关键特性是允许在函数内部定义另一个函数。例如，一个函数可以返回另一个函数作为结果。

当函数在另一个函数内部定义时，其定义环境就不再是全局环境，而是那个外层函数的内部环境。这时，作用域规则开始产生重要影响。

为了说明这一点，我们来看一个构造函数（constructor function）的例子。构造函数是指能够创建并返回另一个函数的函数。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_23.png)

以下是一个构造函数 `make.power` 的示例：

![](img/e648c4e2da59bc8f1aac20de0dcb4731_24.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_25.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_26.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_27.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_28.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_29.png)

```r
make.power <- function(n) {
  power <- function(x) {
    x ^ n
  }
  return(power)
}
```

![](img/e648c4e2da59bc8f1aac20de0dcb4731_30.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_31.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_32.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_34.png)

*   `make.power` 接收一个参数 `n`。
*   在其内部，定义了函数 `power`，它接收参数 `x` 并计算 `x^n`。
*   `make.power` 将 `power` 函数作为返回值。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_35.png)

在 `power` 函数内部：
*   `x` 是形式参数。
*   `n` 是**自由变量**，因为它不是在 `power` 内部定义的。
*   然而，`n` 定义在 `make.power` 函数内部。由于 `power` 的定义环境就是 `make.power` 的内部环境，因此 `power` 可以找到 `n` 的值。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_37.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_38.png)

我们可以这样使用它：

![](img/e648c4e2da59bc8f1aac20de0dcb4731_40.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_41.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_42.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_43.png)

```r
cube <- make.power(3)   # 创建一个计算立方的函数
square <- make.power(2) # 创建一个计算平方的函数

![](img/e648c4e2da59bc8f1aac20de0dcb4731_44.png)

cube(3)   # 返回 27 (3^3)
square(3) # 返回 9 (3^2)
```

现在，我们拥有了一个能够构造多种幂运算函数的通用工具。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_46.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_47.png)

## 探索函数环境

![](img/e648c4e2da59bc8f1aac20de0dcb4731_48.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_49.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_50.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_51.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_52.png)

如何知道一个函数的环境里有什么呢？可以使用 `ls` 和 `get` 函数来查看函数定义环境中的对象。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_53.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_54.png)

```r
# 查看 cube 函数定义环境中的对象
ls(environment(cube))
# 输出: [1] "n" "power"

# 获取该环境中 n 的值
get("n", environment(cube))
# 输出: [1] 3
```

![](img/e648c4e2da59bc8f1aac20de0dcb4731_56.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_57.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_58.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_59.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_60.png)

对于 `square` 函数，其环境中的 `n` 值为 2。这就是 `cube` 和 `square` 知道分别进行三次方和平方运算的原因。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_61.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_62.png)

## 词法作用域 vs. 动态作用域

![](img/e648c4e2da59bc8f1aac20de0dcb4731_64.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_65.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_66.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_68.png)

为了深入理解R的作用域，我们将其与**动态作用域**进行对比。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_70.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_71.png)

考虑以下代码：

![](img/e648c4e2da59bc8f1aac20de0dcb4731_72.png)

```r
y <- 10

![](img/e648c4e2da59bc8f1aac20de0dcb4731_74.png)

f <- function(x) {
  y <- 2
  y^2 + g(x)
}

![](img/e648c4e2da59bc8f1aac20de0dcb4731_75.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_76.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_77.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_78.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_79.png)

g <- function(x) {
  x * y
}
```

在函数 `f` 中：
*   `y` 是局部变量（赋值为2）。
*   `g` 是自由变量。
在函数 `g` 中：
*   `y` 是自由变量。

问题是：调用 `f(3)` 会返回什么？

![](img/e648c4e2da59bc8f1aac20de0dcb4731_81.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_82.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_83.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_84.png)

*   **在词法作用域（R使用）下**：`g` 函数中的 `y` 值在其**定义环境**（即全局环境）中查找，因此 `y = 10`。计算过程为：`2^2 + (3 * 10) = 34`。
*   **在动态作用域下**：`g` 函数中的 `y` 值在其**调用环境**（即 `f` 的内部环境）中查找，因此 `y = 2`。计算过程为：`2^2 + (3 * 2) = 10`。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_85.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_86.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_87.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_88.png)

当函数在全局环境中定义并从全局环境调用时，定义环境和调用环境相同，这有时会让词法作用域看起来像动态作用域。

请看另一个例子：

![](img/e648c4e2da59bc8f1aac20de0dcb4731_90.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_91.png)

```r
g <- function(x) {
  a <- 3
  x + a + y
}
```

![](img/e648c4e2da59bc8f1aac20de0dcb4731_92.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_93.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_94.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_95.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_96.png)

在 `g` 中，`y` 是自由变量。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_98.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_99.png)

```r
g(2) # 报错：找不到对象 'y'
y <- 3
g(2) # 返回 8 (2 + 3 + 3)
```

![](img/e648c4e2da59bc8f1aac20de0dcb4731_101.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_102.png)

虽然看起来 `y` 的值是在调用时从全局工作空间获取的，但实际上是因为 `g` 的定义环境就是全局环境。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_103.png)

## 词法作用域的意义与影响

词法作用域并非R独有，Scheme、Perl、Python、Common Lisp等语言也支持它。这是一种强大且常见的编程语言特性。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_105.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_106.png)

R采用词法作用域带来了两个主要影响：

![](img/e648c4e2da59bc8f1aac20de0dcb4731_107.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_108.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_109.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_110.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_111.png)

1.  **所有对象必须存储在内存中**：由于作用域规则和环境链的复杂性，很难在物理内存之外实现这个模型。这意味着处理超大型数据集时，将数据全部读入内存可能成为挑战。
2.  **函数必须携带指向其定义环境的指针**：这使得R的对象模型比那些所有函数都在同一全局环境中查找自由变量的语言（如早期的S-PLUS）更为复杂，但也因此更加强大和灵活。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_112.png)

## 总结

![](img/e648c4e2da59bc8f1aac20de0dcb4731_114.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_115.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_116.png)

本节课中，我们一起学习了R语言的**词法作用域规则**。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_117.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_118.png)

我们了解到：
*   R函数中的自由变量在其**定义环境**中查找，而非调用环境。
*   通过**构造函数**，我们可以在一个函数内部定义并返回另一个函数，创建出功能特定但共享某些状态的函数。
*   词法作用域与动态作用域的关键区别在于变量查找的环境不同。
*   词法作用域是R语言强大功能（如闭包）的基础，但也要求所有数据对象常驻内存。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_120.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_121.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_122.png)

理解这些规则有助于你编写更模块化、更强大的R代码，并能够预测和调试函数的行为。