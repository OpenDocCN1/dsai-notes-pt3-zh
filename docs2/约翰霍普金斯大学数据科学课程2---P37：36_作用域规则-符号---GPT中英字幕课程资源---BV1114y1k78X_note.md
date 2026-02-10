# 课程2：R编程 - P37：作用域规则与符号绑定 🔍

![](img/99a0f17c50b1188664eeae0ea2cd59aa_0.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_1.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_3.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_4.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_5.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_6.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_7.png)

在本节课中，我们将要学习R语言中一个至关重要的概念：**作用域规则**。具体来说，我们将探讨当R函数执行时，它如何为函数体内出现的符号（变量名）绑定一个具体的值。理解这个过程对于编写和调试R代码至关重要。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_9.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_10.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_11.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_12.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_13.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_14.png)

---

![](img/99a0f17c50b1188664eeae0ea2cd59aa_16.png)

## 概述：符号绑定与搜索过程

![](img/99a0f17c50b1188664eeae0ea2cd59aa_17.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_18.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_19.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_20.png)

在R中，当一个函数运行时，它需要为函数体内出现的每个符号找到对应的值。这个过程称为**符号绑定**。R通过搜索一系列**环境**来完成这个绑定。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_22.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_23.png)

环境可以被视为一系列**符号与值的配对列表**。例如，符号 `x` 可能绑定到值 `3.14`，符号 `y` 可能绑定到一个数据框。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_24.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_25.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_26.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_27.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_28.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_29.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_30.png)

上一节我们介绍了符号绑定的基本概念，本节中我们来看看R是如何具体执行搜索的。

---

![](img/99a0f17c50b1188664eeae0ea2cd59aa_32.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_33.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_34.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_35.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_36.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_37.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_38.png)

## 搜索列表与绑定顺序

![](img/99a0f17c50b1188664eeae0ea2cd59aa_39.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_40.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_41.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_42.png)

R在寻找符号对应的值时，遵循一个特定的搜索路径，即**搜索列表**。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_44.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_45.png)

以下是搜索过程的核心步骤：

![](img/99a0f17c50b1188664eeae0ea2cd59aa_46.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_47.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_48.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_49.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_50.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_51.png)

1.  **首先搜索全局环境**：全局环境就是你的工作空间，包含你定义或加载到R中的所有对象。如果在这里找到了匹配的符号，就使用其绑定的值。
2.  **然后按顺序搜索已加载的包**：如果在全局环境中没有找到，R会按顺序搜索 `search()` 列表中的每个包的命名空间。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_53.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_54.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_55.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_56.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_57.png)

搜索列表的顺序至关重要。默认情况下，列表的第一个元素总是**全局环境**，最后一个元素总是 **`base` 包**。用户通过 `library()` 函数加载的包，其命名空间会被插入到列表的**第二个位置**（紧随全局环境之后），其他包则依次后移。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_59.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_60.png)

> **注意**：R对函数和非函数对象有独立的命名空间。这意味着你可以同时拥有一个名为 `c` 的向量和一个名为 `c` 的函数（连接函数），它们不会互相冲突。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_61.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_62.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_63.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_64.png)

---

![](img/99a0f17c50b1188664eeae0ea2cd59aa_66.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_67.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_68.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_69.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_70.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_71.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_72.png)

## 词法作用域：自由变量的绑定规则

![](img/99a0f17c50b1188664eeae0ea2cd59aa_74.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_75.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_76.png)

R的作用域规则是其区别于原始S语言的主要特性。R采用**词法作用域**（也称为静态作用域）。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_77.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_78.png)

在函数内部，变量分为两种：
*   **形式参数**：在函数定义时声明的参数。
*   **自由变量**：在函数体中使用，但既不是形式参数，也未在函数内部定义的变量。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_80.png)

词法作用域的核心规则是：**自由变量的值，在定义该函数的环境中寻找**。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_81.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_82.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_83.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_84.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_85.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_86.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_87.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_88.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_89.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_90.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_91.png)

让我们通过一个例子来理解：

![](img/99a0f17c50b1188664eeae0ea2cd59aa_93.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_94.png)

```r
f <- function(x, y) {
  x^2 + y / z
}
```
在这个函数中，`x` 和 `y` 是形式参数，而 `z` 是一个自由变量。当调用 `f(2, 3)` 时，R如何确定 `z` 的值呢？

![](img/99a0f17c50b1188664eeae0ea2cd59aa_96.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_97.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_98.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_99.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_100.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_101.png)

根据词法作用域规则，R会去到**定义函数 `f` 的环境**（假设是在全局环境中定义的）中寻找符号 `z` 的值。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_103.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_104.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_105.png)

---

## 环境层级与搜索链

![](img/99a0f17c50b1188664eeae0ea2cd59aa_107.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_108.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_109.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_110.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_111.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_112.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_113.png)

每个环境都有一个**父环境**，从而形成了一条环境链。唯一的例外是**空环境**，它没有父环境。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_115.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_116.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_117.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_118.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_120.png)

当在函数中遇到自由变量时，R的搜索过程如下：

![](img/99a0f17c50b1188664eeae0ea2cd59aa_122.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_123.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_124.png)

1.  首先，在**定义该函数的环境**中查找。
2.  如果未找到，则进入该环境的**父环境**中查找。
3.  重复步骤2，沿着环境链向上搜索，直到达**顶层环境**（对于全局环境中定义的函数，顶层环境通常是全局环境本身；对于包中定义的函数，则是该包的命名空间）。
4.  到达顶层环境后，搜索会继续沿着 `search()` 列表向下进行，直到检查完所有包（包括 `base` 包）。
5.  如果搜索到空环境仍未找到该符号，R就会抛出一个错误。

这种将函数与其定义环境关联起来的结构被称为**函数闭包**，它是R中许多高级编程技术的基础。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_126.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_127.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_128.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_129.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_130.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_131.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_132.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_133.png)

---

![](img/99a0f17c50b1188664eeae0ea2cd59aa_135.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_136.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_137.png)

## 总结

![](img/99a0f17c50b1188664eeae0ea2cd59aa_138.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_139.png)

本节课中我们一起学习了R语言的作用域规则与符号绑定机制。

![](img/99a0f17c50b1188664eeae0ea2cd59aa_141.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_142.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_143.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_144.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_145.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_146.png)

![](img/99a0f17c50b1188664eeae0ea2cd59aa_148.png)

我们了解到，R通过搜索一系列环境来为符号绑定值，其核心是**搜索列表**和**词法作用域规则**。词法作用域规定，自由变量的值在其**函数被定义的环境中**确定，并沿着环境链向上查找。理解这些规则有助于我们预测函数的行为，避免变量名冲突，并编写出更清晰、更可靠的R代码。