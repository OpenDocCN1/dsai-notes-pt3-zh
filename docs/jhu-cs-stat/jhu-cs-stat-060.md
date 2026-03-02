#  060：R语言中的期望值教程 📊

在本教程中，我们将学习如何在R语言中计算期望值、方差和矩母函数。我们将从数值积分的基础概念开始，逐步构建计算期望值和方差的函数，并最终实现矩母函数的计算。本教程旨在通过简单的代码示例，帮助初学者理解这些统计概念在R中的实现方式。

---

## 数值积分入门 🔢

上一节我们介绍了期望值的理论基础，本节中我们来看看如何在R中通过数值积分来近似计算积分。数值积分是一种通过将积分区间划分为多个小矩形并求和来近似积分值的方法。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_1.png)

以下是创建一个简单数值积分函数的步骤：

```r
# 定义数值积分函数
nu_integrate <- function(f, a, b, n=30) {
  dx <- (b - a) / n  # 每个矩形的宽度
  x <- seq(a, b - dx, by=dx)  # 生成x值序列
  sum(f(x) * dx)  # 黎曼和
}
```

![](img/4930c7043debccb1a1d9c7741dd3d7ed_3.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_4.png)

我们可以用标准正态分布的概率密度函数来测试这个函数。积分区间从-1.96到1.96，这覆盖了标准正态分布下约95%的面积。

```r
# 测试函数：计算标准正态分布在[-1.96, 1.96]区间下的面积
result <- nu_integrate(dnorm, -1.96, 1.96)
print(result)  # 输出应接近0.95
```

为了更直观地理解数值积分的过程，我们可以创建一个可视化图形。以下代码将绘制正态分布曲线，并高亮显示黎曼和中的一个矩形。

```r
# 加载ggplot2库用于绘图
library(ggplot2)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_6.png)

# 设置参数
f <- dnorm
a <- -1.96
b <- 1.96
n <- 30
dx <- (b - a) / n
x <- seq(a, b - dx, by=dx)

# 创建数据框
df <- data.frame(x = x, y = f(x))

![](img/4930c7043debccb1a1d9c7741dd3d7ed_8.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_9.png)

# 创建绘图
p <- ggplot() +
  stat_function(fun = dnorm, args = list(mean=0, sd=1), color="blue") +
  geom_rect(data=df, aes(xmin=x, xmax=x+dx, ymin=0, ymax=y), fill="red", alpha=0.3) +
  labs(title="数值积分可视化 (黎曼和)", x="x", y="密度 f(x)") +
  theme_minimal()

![](img/4930c7043debccb1a1d9c7741dd3d7ed_10.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_12.png)

# 高亮第7个矩形（可选）
highlight_rect <- 7
p <- p + geom_rect(data=df[highlight_rect, ], aes(xmin=x, xmax=x+dx, ymin=0, ymax=y), fill="green", alpha=0.7)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_14.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_16.png)

print(p)
```

你可以尝试改变`n`的值（例如增加到100），观察矩形数量增加如何使近似值更精确。也可以尝试使用其他分布函数，如`dexp`（指数分布）或`dgamma`（伽马分布），来练习数值积分。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_18.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_19.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_21.png)

---

## 使用内置函数进行积分 📈

上一节我们手动实现了数值积分，本节中我们来看看R语言内置的、更精确的积分函数`integrate`。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_23.png)

`integrate`函数使用更先进的算法进行数值积分，通常比简单的黎曼和更精确、更高效。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_24.png)

```r
# 使用内置integrate函数计算相同积分
exact_result <- integrate(dnorm, lower = -1.96, upper = 1.96)
print(exact_result)
# 输出包含积分值和绝对误差估计
```

现在，让我们利用这个强大的工具来计算连续型随机变量的期望值。连续型随机变量X的期望值公式为：
**E[X] = ∫ x * f(x) dx**，积分区间为整个定义域。

```r
# 计算均值为7的正态分布的期望值
expected_value <- integrate(function(x) { x * dnorm(x, mean = 7) }, lower = -Inf, upper = Inf)
print(expected_value)  # 结果应接近7
```

为了使代码更简洁和可复用，我们可以将计算期望值的逻辑封装成一个函数。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_26.png)

```r
# 创建计算期望值的通用函数
EX <- function(density_func, ...) {
  # density_func: 概率密度函数，如dnorm, dexp
  # ...: 传递给密度函数的参数，如mean, rate
  f <- function(x) {
    x * density_func(x, ...)
  }
  result <- integrate(f, lower = -Inf, upper = Inf)
  return(result$value)  # 返回积分值
}

![](img/4930c7043debccb1a1d9c7741dd3d7ed_27.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_28.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_29.png)

# 使用函数计算期望值
mean_norm <- EX(dnorm, mean = 7)
print(mean_norm)

# 尝试计算指数分布(rate=0.5)的期望值
mean_exp <- EX(dexp, rate = 0.5)
print(mean_exp)  # 指数分布的期望值为1/rate，此处应为2
```

![](img/4930c7043debccb1a1d9c7741dd3d7ed_31.png)

---

![](img/4930c7043debccb1a1d9c7741dd3d7ed_33.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_34.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_35.png)

## 推广到函数变换与矩母函数 🧮

上一节我们计算了随机变量本身的期望值，本节中我们来看看如何计算随机变量函数的期望值，并由此引出矩母函数。

随机变量函数g(X)的期望值公式为：
**E[g(X)] = ∫ g(x) * f(x) dx**

我们可以创建一个通用函数来计算任何变换g(x)下的期望值。

```r
# 创建计算函数变换期望值的通用函数
E_transform <- function(g, density_func, ...) {
  # g: 变换函数，例如 function(x) { x^2 }
  # density_func: 概率密度函数
  # ...: 密度函数参数
  f <- function(x) {
    g(x) * density_func(x, ...)
  }
  result <- integrate(f, lower = -Inf, upper = Inf)
  return(result$value)
}
```

![](img/4930c7043debccb1a1d9c7741dd3d7ed_37.png)

矩母函数是概率论中的一个核心概念，定义为 **M(t) = E[e^(tX)]**。我们可以用上面的函数来计算它。

```r
# 定义矩母函数计算函数
moment_gen <- function(t, density_func, ...) {
  g <- function(x) {
    exp(t * x)
  }
  return(E_transform(g, density_func, ...))
}

![](img/4930c7043debccb1a1d9c7741dd3d7ed_39.png)

# 计算正态分布(mean=5, sd=3)在t=0.1时的矩母函数值
mgf_value <- moment_gen(t = 0.1, dnorm, mean = 5, sd = 3)
print(mgf_value)
```

![](img/4930c7043debccb1a1d9c7741dd3d7ed_41.png)

矩母函数之所以强大，是因为它的各阶导数在t=0处的值给出了分布的各阶矩。特别地，一阶矩是期望值，二阶矩与方差有关。

```r
# 计算一阶矩（期望值）的另一种方法：使用矩母函数在t=0处的导数
# 数值求导计算一阶矩
first_moment <- E_transform(function(x) { x }, dnorm, mean=5, sd=3)
print(first_moment)  # 应等于5

![](img/4930c7043debccb1a1d9c7741dd3d7ed_43.png)

# 我们也可以将期望值函数与矩的概念统一命名
E <- function(density_func, ...) {
  EX(density_func, ...)
}
print(E(dnorm, mean=5, sd=3))
```

---

## 计算方差 📊

上一节我们利用期望值和矩母函数计算了一阶矩，本节中我们来看看如何计算二阶矩和方差。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_45.png)

随机变量X的方差公式为：
**Var(X) = E[X^2] - (E[X])^2**

我们可以利用之前定义的`E_transform`函数来计算`E[X^2]`（即二阶矩）。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_47.png)

```r
# 计算方差函数
variance <- function(density_func, ...) {
  # 计算期望值 E[X]
  mu <- E(density_func, ...)
  # 计算二阶矩 E[X^2]
  second_moment <- E_transform(function(x) { x^2 }, density_func, ...)
  # 方差 = E[X^2] - (E[X])^2
  var <- second_moment - mu^2
  return(var)
}

![](img/4930c7043debccb1a1d9c7741dd3d7ed_49.png)

# 计算正态分布(mean=5, sd=3)的方差
var_norm <- variance(dnorm, mean=5, sd=3)
print(var_norm)  # 应等于9 (即3^2)

# 计算指数分布(rate=0.5)的方差
var_exp <- variance(dexp, rate=0.5)
print(var_exp)  # 指数分布的方差为1/(rate^2)，此处应为4
```

![](img/4930c7043debccb1a1d9c7741dd3d7ed_51.png)

---

![](img/4930c7043debccb1a1d9c7741dd3d7ed_53.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_54.png)

## 总结 🎯

本节课中我们一起学习了在R语言中处理期望值、方差和矩母函数的核心技能。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_56.png)

我们首先从**数值积分**入手，通过构建黎曼和函数并可视化，理解了积分近似计算的基本原理。接着，我们引入了R内置的`integrate`函数，它提供了更精确和高效的积分计算。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_58.png)

利用积分，我们定义了计算**期望值** `EX` 的通用函数，并推广到计算任意函数变换 `E_transform` 的期望值。在此基础上，我们实现了**矩母函数** `moment_gen` 的计算，矩母函数是推导分布各阶矩的有力工具。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_59.png)

最后，我们结合期望值和二阶矩，构建了计算**方差**的函数 `variance`。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_61.png)

本教程提供的代码框架是通用的，鼓励你将其应用于不同的概率分布（如伽马分布、贝塔分布），并通过改变参数来加深对统计概念与R编程的理解。理论部分请结合课程讲座内容，以形成完整的知识体系。