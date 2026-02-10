# 课程2：《R编程》｜第42课：循环函数 lapply 🌀

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_0.png)

在本节课中，我们将要学习R语言中一组非常强大的工具——循环函数。它们能让我们用极少的代码完成大量的循环操作，尤其是在交互式环境中非常高效。我们将重点介绍 `lapply` 函数，并了解其家族成员。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_2.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_3.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_4.png)

## 概述：什么是循环函数？🤔

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_5.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_6.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_7.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_8.png)

循环函数是R语言中最强大的函数之一，它们使得在交互式环境中进行循环操作变得非常容易。循环函数的核心思想是，对一个对象或一组对象执行循环操作，从而用极少的代码完成大量工作，减少在命令行中的输入。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_10.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_11.png)

我们已经学习过 `for` 循环和 `while` 循环，它们虽然有效，但在某些方面不够紧凑。R语言中有几个关键的循环函数，它们的名字中通常包含 `apply`。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_13.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_14.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_15.png)

以下是主要的循环函数：

*   **`lapply`**： 对列表（list）的每个元素应用一个函数。
*   **`sapply`**： `lapply` 的简化版本，尝试简化返回结果。
*   **`apply`**： 对数组（如矩阵）的维度（行或列）应用函数。
*   **`tapply`**： 对向量的子集应用函数。
*   **`mapply`**： `lapply` 的多变量版本。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_17.png)

此外，还有一个名为 `split` 的函数，它本身不应用任何函数，但常与 `lapply` 或 `sapply` 结合使用，用于将对象分割成子部分。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_18.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_19.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_20.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_21.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_22.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_23.png)

接下来，我们将深入探讨其中最核心的函数：`lapply`。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_24.png)

## 深入 `lapply` 函数 🎯

`lapply` 函数的基本思想是：你有一个对象列表，希望遍历这个列表，并对列表中的**每一个元素**应用一个指定的函数。这是一个非常通用的概念，能够用极少的代码完成大量计算。

### `lapply` 的参数与工作原理

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_26.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_27.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_28.png)

`lapply` 函数接受三个基本参数：

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_29.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_30.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_31.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_32.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_33.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_34.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_35.png)

1.  **`x`**： 一个列表。
2.  **`FUN`**： 一个函数（或函数名）。
3.  **`...`**： 其他参数，这些参数会被传递给 `FUN` 函数。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_36.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_37.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_39.png)

如果 `x` 不是一个列表，`lapply` 会尝试将其强制转换为列表。如果无法转换，则会报错。

`lapply` 的工作流程如下：它接收一个列表（列表可以包含任何类型的对象，如向量、矩阵、数据框等），对列表中的每个元素应用 `FUN` 函数。这个函数会为每个元素返回一个结果（可能与原始元素的类型不同，例如，输入是向量，输出可能是标量）。最后，`lapply` 将所有返回的结果**组装成一个新的列表**并返回。

**关键点**：`lapply` **总是返回一个列表**。输入可能不是列表，但会被强制转换；输出则一定是一个列表。

### `lapply` 基础示例

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_41.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_42.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_43.png)

让我们看一个简单的例子。首先创建一个包含两个元素的列表：

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_44.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_45.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_46.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_47.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_48.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_49.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_50.png)

```r
x <- list(a = 1:5, b = rnorm(10))
```

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_51.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_52.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_54.png)

这个列表 `x` 包含两个元素：
*   `a`： 一个从1到5的序列。
*   `b`： 10个来自标准正态分布的随机数。

现在，我们想遍历这个列表，并对每个元素计算其平均值（`mean`）。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_56.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_57.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_58.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_59.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_61.png)

```r
lapply(x, mean)
```

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_63.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_64.png)

执行上述代码后，`lapply` 会返回一个新的列表。这个新列表保留了原始列表的名称（`a` 和 `b`），但每个元素的值变成了对应原始元素的平均值。

### 使用 `...` 传递额外参数

`lapply` 的 `...` 参数允许我们向被应用的函数传递额外的参数。例如，我们想对序列 `1:4` 中的每个数字 `n`，生成 `n` 个随机均匀分布数。默认的 `runif(n)` 生成0到1之间的数。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_66.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_67.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_68.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_69.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_70.png)

```r
x <- 1:4
lapply(x, runif)
```

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_71.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_72.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_73.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_74.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_75.png)

上述代码会生成一个列表，其中第一个元素是1个随机数，第二个是2个随机数的向量，依此类推。

如果我们希望生成的随机数在0到10之间，就需要修改 `runif` 函数的 `min` 和 `max` 参数。这可以通过 `...` 实现：

```r
lapply(x, runif, min = 0, max = 10)
```

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_77.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_78.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_79.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_80.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_81.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_82.png)

现在，生成的列表中的随机数都介于0和10之间。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_83.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_84.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_85.png)

## 匿名函数与 `lapply` 🕵️‍♂️

`lapply` 及其相关函数大量使用**匿名函数**。匿名函数是指没有名字、在调用时临时定义的函数。当你需要执行的操作没有现成的函数时，匿名函数就非常有用。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_87.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_88.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_89.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_90.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_91.png)

假设我们有一个包含两个矩阵的列表：

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_92.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_93.png)

```r
x <- list(a = matrix(1:4, 2, 2), b = matrix(1:6, 3, 2))
```

我们想提取每个矩阵的第一列。虽然没有一个现成的“提取第一列”函数，但我们可以用匿名函数轻松实现：

```r
lapply(x, function(elt) elt[, 1])
```

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_95.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_96.png)

这里，我们在 `lapply` 调用内部直接定义了一个函数：`function(elt) elt[, 1]`。这个函数接受一个参数 `elt`（代表列表中的每个元素），并返回该矩阵的第一列（`elt[, 1]`）。`lapply` 执行完毕后，这个临时函数就“消失”了。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_97.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_98.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_99.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_100.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_101.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_102.png)

## `sapply`：简化结果的 `lapply` ✨

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_103.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_104.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_105.png)

`lapply` 总是返回列表，但有时我们可能希望得到更简单的数据结构，比如向量或矩阵。`sapply` 就是 `lapply` 的一个变体，它会尝试**简化** `lapply` 的结果。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_107.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_108.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_109.png)

`simplify` 的规则如下：
*   如果结果列表中的每个元素都是**长度为1**的向量，`sapply` 会将其简化为一个**向量**。
*   如果结果列表中的每个元素都是**长度相同**的向量，`sapply` 会将其简化为一个**矩阵**。
*   如果无法简化（例如，返回的元素类型或长度差异很大），`sapply` 会像 `lapply` 一样返回一个列表。

回顾之前计算列表元素平均值的例子：

```r
x <- list(a = 1:5, b = rnorm(10), c = rnorm(20, 1), d = rnorm(100, 5))
lapply(x, mean) # 返回一个列表，每个元素是一个数字
sapply(x, mean) # 返回一个包含四个数字的向量
```

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_111.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_112.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_113.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_114.png)

使用 `sapply` 后，我们直接得到了一个数值向量，这通常比处理列表更方便。如果直接对列表 `x` 调用 `mean` 函数，由于 `mean` 并非为列表设计，你会得到警告和 `NA` 值。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_115.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_116.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_117.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_118.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_119.png)

## 总结 📚

本节课我们一起学习了R语言中强大的循环函数，重点是 `lapply`。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_121.png)

*   **循环函数**（如 `lapply`, `sapply`, `apply`）能用紧凑的代码替代传统的循环结构。
*   **`lapply`** 函数遍历一个列表，对每个元素应用指定函数，并**总是返回一个列表**。其核心参数是列表 `x`、函数 `FUN` 和用于传递额外参数的 `...`。
*   **匿名函数**允许我们在调用 `lapply` 时临时定义所需的功能，非常灵活。
*   **`sapply`** 是 `lapply` 的友好版本，它会尝试将返回的列表简化为向量或矩阵，使结果更易于处理。

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_122.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_123.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_124.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_125.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_126.png)

![](img/4d98bd5e9bf302dddd4ebcbf816001ea_127.png)

掌握 `lapply` 及其家族是高效进行R编程和数据操作的关键一步。在接下来的课程中，我们将继续探索其他 `apply` 族函数。