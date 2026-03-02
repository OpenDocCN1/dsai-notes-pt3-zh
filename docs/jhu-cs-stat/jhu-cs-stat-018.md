#  018：R语言概率探索教程 🎲

![](img/37752e25380dacd3a400858e09ee6586_0.png)

在本教程中，我们将学习如何使用R语言编程来探索概率。我们将从设置工作环境开始，逐步学习如何定义样本空间、进行模拟实验、处理集合运算，并最终计算事件的概率。

![](img/37752e25380dacd3a400858e09ee6586_2.png)

![](img/37752e25380dacd3a400858e09ee6586_3.png)

![](img/37752e25380dacd3a400858e09ee6586_5.png)

![](img/37752e25380dacd3a400858e09ee6586_7.png)

## 准备工作：加载工具包与函数

![](img/37752e25380dacd3a400858e09ee6586_9.png)

![](img/37752e25380dacd3a400858e09ee6586_10.png)

在开始之前，我们需要加载一些必要的R包和自定义函数。这些工具集中在一个名为`Stat tools`的文件中，通过`source`命令运行，可以一次性加载所有需要的功能。这些自定义函数是为特定任务编写的，不会在全局环境中自动可用。

![](img/37752e25380dacd3a400858e09ee6586_11.png)

![](img/37752e25380dacd3a400858e09ee6586_13.png)

```r
# 清除当前环境中的所有变量
rm(list = ls())

![](img/37752e25380dacd3a400858e09ee6586_15.png)

![](img/37752e25380dacd3a400858e09ee6586_16.png)

# 加载自定义函数和所需包
source("Stat_tools.R")
```

![](img/37752e25380dacd3a400858e09ee6586_17.png)

![](img/37752e25380dacd3a400858e09ee6586_18.png)

运行上述代码后，所需的包和函数就被加载到当前R会话中，可供后续使用。

## 定义样本空间

![](img/37752e25380dacd3a400858e09ee6586_20.png)

![](img/37752e25380dacd3a400858e09ee6586_21.png)

![](img/37752e25380dacd3a400858e09ee6586_22.png)

样本空间是一个实验所有可能结果的集合。在R中，我们可以用多种方式定义它。

![](img/37752e25380dacd3a400858e09ee6586_24.png)

### 使用数据框定义

![](img/37752e25380dacd3a400858e09ee6586_26.png)

![](img/37752e25380dacd3a400858e09ee6586_27.png)

![](img/37752e25380dacd3a400858e09ee6586_29.png)

我们可以使用`data.frame`来创建一个简单的样本空间。例如，定义一个物体落地后可能的状态：

![](img/37752e25380dacd3a400858e09ee6586_31.png)

![](img/37752e25380dacd3a400858e09ee6586_33.png)

```r
lands <- data.frame(outcome = c("up", "down", "side"))
lands
```

![](img/37752e25380dacd3a400858e09ee6586_35.png)

![](img/37752e25380dacd3a400858e09ee6586_36.png)

![](img/37752e25380dacd3a400858e09ee6586_37.png)

![](img/37752e25380dacd3a400858e09ee6586_39.png)

运行后，变量`lands`就包含了三个可能的结果：`up`、`down`和`side`。

![](img/37752e25380dacd3a400858e09ee6586_41.png)

![](img/37752e25380dacd3a400858e09ee6586_43.png)

![](img/37752e25380dacd3a400858e09ee6586_44.png)

![](img/37752e25380dacd3a400858e09ee6586_46.png)

### 使用`sample`函数模拟

![](img/37752e25380dacd3a400858e09ee6586_48.png)

![](img/37752e25380dacd3a400858e09ee6586_49.png)

![](img/37752e25380dacd3a400858e09ee6586_51.png)

对于掷骰子或抛硬币这类有固定数量结果的实验，我们可以使用`sample`函数进行模拟。

![](img/37752e25380dacd3a400858e09ee6586_53.png)

![](img/37752e25380dacd3a400858e09ee6586_55.png)

![](img/37752e25380dacd3a400858e09ee6586_57.png)

以下是模拟掷一个六面骰子30次的方法：

![](img/37752e25380dacd3a400858e09ee6586_58.png)

![](img/37752e25380dacd3a400858e09ee6586_60.png)

![](img/37752e25380dacd3a400858e09ee6586_62.png)

```r
die <- sample(1:6, size = 30, replace = TRUE)
die
```

![](img/37752e25380dacd3a400858e09ee6586_64.png)

![](img/37752e25380dacd3a400858e09ee6586_65.png)

同样地，我们可以模拟抛一枚均匀硬币30次：

![](img/37752e25380dacd3a400858e09ee6586_67.png)

![](img/37752e25380dacd3a400858e09ee6586_68.png)

![](img/37752e25380dacd3a400858e09ee6586_70.png)

```r
coin <- sample(c("Heads", "Tails"), size = 30, replace = TRUE)
coin
```

![](img/37752e25380dacd3a400858e09ee6586_72.png)

![](img/37752e25380dacd3a400858e09ee6586_73.png)

![](img/37752e25380dacd3a400858e09ee6586_74.png)

![](img/37752e25380dacd3a400858e09ee6586_76.png)

![](img/37752e25380dacd3a400858e09ee6586_77.png)

### 使用`prob`包中的函数

![](img/37752e25380dacd3a400858e09ee6586_79.png)

![](img/37752e25380dacd3a400858e09ee6586_80.png)

![](img/37752e25380dacd3a400858e09ee6586_82.png)

`prob`包（在`source`时已加载）提供了更便捷的函数来生成标准实验的样本空间。

![](img/37752e25380dacd3a400858e09ee6586_84.png)

![](img/37752e25380dacd3a400858e09ee6586_86.png)

![](img/37752e25380dacd3a400858e09ee6586_88.png)

例如，生成抛一次硬币的样本空间：

![](img/37752e25380dacd3a400858e09ee6586_90.png)

![](img/37752e25380dacd3a400858e09ee6586_92.png)

![](img/37752e25380dacd3a400858e09ee6586_94.png)

```r
tosscoin(times = 1)
```

![](img/37752e25380dacd3a400858e09ee6586_96.png)

![](img/37752e25380dacd3a400858e09ee6586_97.png)

![](img/37752e25380dacd3a400858e09ee6586_98.png)

生成抛三次硬币的样本空间（此时样本空间大小为2³ = 8）：

![](img/37752e25380dacd3a400858e09ee6586_99.png)

![](img/37752e25380dacd3a400858e09ee6586_101.png)

![](img/37752e25380dacd3a400858e09ee6586_103.png)

```r
tosscoin(times = 3)
```

![](img/37752e25380dacd3a400858e09ee6586_105.png)

![](img/37752e25380dacd3a400858e09ee6586_107.png)

![](img/37752e25380dacd3a400858e09ee6586_109.png)

对于掷骰子，也有对应的函数：

![](img/37752e25380dacd3a400858e09ee6586_111.png)

![](img/37752e25380dacd3a400858e09ee6586_112.png)

![](img/37752e25380dacd3a400858e09ee6586_113.png)

![](img/37752e25380dacd3a400858e09ee6586_115.png)

![](img/37752e25380dacd3a400858e09ee6586_117.png)

```r
# 掷一个骰子
rolldie(times = 1)
# 掷两个骰子（样本空间大小为6² = 36）
rolldie(times = 2)
```

![](img/37752e25380dacd3a400858e09ee6586_119.png)

![](img/37752e25380dacd3a400858e09ee6586_121.png)

![](img/37752e25380dacd3a400858e09ee6586_123.png)

![](img/37752e25380dacd3a400858e09ee6586_125.png)

### 扑克牌与抽球实验

![](img/37752e25380dacd3a400858e09ee6586_127.png)

![](img/37752e25380dacd3a400858e09ee6586_129.png)

![](img/37752e25380dacd3a400858e09ee6586_130.png)

![](img/37752e25380dacd3a400858e09ee6586_132.png)

`prob`包还内置了扑克牌的样本空间：

![](img/37752e25380dacd3a400858e09ee6586_133.png)

![](img/37752e25380dacd3a400858e09ee6586_135.png)

![](img/37752e25380dacd3a400858e09ee6586_136.png)

```r
# 查看牌堆的前几张牌
head(cards())
# 查看牌堆的最后几张牌
tail(cards())
```

![](img/37752e25380dacd3a400858e09ee6586_138.png)

![](img/37752e25380dacd3a400858e09ee6586_139.png)

![](img/37752e25380dacd3a400858e09ee6586_140.png)

对于从瓮中抽球的经典概率实验，我们可以使用`urnsamples`函数，并指定是否放回：

![](img/37752e25380dacd3a400858e09ee6586_142.png)

![](img/37752e25380dacd3a400858e09ee6586_143.png)

![](img/37752e25380dacd3a400858e09ee6586_144.png)

![](img/37752e25380dacd3a400858e09ee6586_146.png)

```r
# 从装有1,2,3三个球的瓮中抽两个球，有放回
urnsamples(1:3, size = 2, replace = TRUE)
# 从瓮中抽两个球，无放回
urnsamples(1:3, size = 2, replace = FALSE)
```
**注意**：有放回时，可能抽到相同数字（如`(1,1)`）；无放回时，则不可能。

![](img/37752e25380dacd3a400858e09ee6586_148.png)

![](img/37752e25380dacd3a400858e09ee6586_150.png)

![](img/37752e25380dacd3a400858e09ee6586_152.png)

![](img/37752e25380dacd3a400858e09ee6586_154.png)

## 集合运算：并集、交集与差集

![](img/37752e25380dacd3a400858e09ee6586_155.png)

![](img/37752e25380dacd3a400858e09ee6586_157.png)

![](img/37752e25380dacd3a400858e09ee6586_158.png)

在定义了样本空间后，我们经常需要处理事件的集合。R可以方便地进行集合运算。

![](img/37752e25380dacd3a400858e09ee6586_160.png)

![](img/37752e25380dacd3a400858e09ee6586_162.png)

![](img/37752e25380dacd3a400858e09ee6586_163.png)

![](img/37752e25380dacd3a400858e09ee6586_164.png)

首先，让我们以一副标准扑克牌（不含大小王）为例建立样本空间：

![](img/37752e25380dacd3a400858e09ee6586_166.png)

```r
S <- cards(makespace = FALSE)
```

![](img/37752e25380dacd3a400858e09ee6586_168.png)

![](img/37752e25380dacd3a400858e09ee6586_169.png)

![](img/37752e25380dacd3a400858e09ee6586_170.png)

![](img/37752e25380dacd3a400858e09ee6586_171.png)

![](img/37752e25380dacd3a400858e09ee6586_172.png)

假设我们定义两个事件：
*   **事件A**：抽到红桃（Hearts）。
*   **事件B**：抽到点数为5到8的牌。

![](img/37752e25380dacd3a400858e09ee6586_174.png)

![](img/37752e25380dacd3a400858e09ee6586_176.png)

```r
A <- subset(S, suit == "Heart")
B <- subset(S, rank %in% 5:8)
```

![](img/37752e25380dacd3a400858e09ee6586_178.png)

![](img/37752e25380dacd3a400858e09ee6586_179.png)

现在，我们可以对这两个集合进行运算：

![](img/37752e25380dacd3a400858e09ee6586_180.png)

以下是计算**并集**（A或B发生）的方法：

![](img/37752e25380dacd3a400858e09ee6586_182.png)

![](img/37752e25380dacd3a400858e09ee6586_183.png)

![](img/37752e25380dacd3a400858e09ee6586_184.png)

![](img/37752e25380dacd3a400858e09ee6586_186.png)

![](img/37752e25380dacd3a400858e09ee6586_188.png)

```r
union(A, B)
```

![](img/37752e25380dacd3a400858e09ee6586_190.png)

以下是计算**交集**（A和B同时发生）的方法：

![](img/37752e25380dacd3a400858e09ee6586_192.png)

![](img/37752e25380dacd3a400858e09ee6586_194.png)

```r
intersect(A, B)
```

![](img/37752e25380dacd3a400858e09ee6586_196.png)

![](img/37752e25380dacd3a400858e09ee6586_198.png)

以下是计算**差集**（在A中但不在B中）的方法：

![](img/37752e25380dacd3a400858e09ee6586_200.png)

![](img/37752e25380dacd3a400858e09ee6586_201.png)

```r
setdiff(A, B)
```
**注意**：`setdiff(A, B)`与`setdiff(B, A)`的结果通常不同。

![](img/37752e25380dacd3a400858e09ee6586_203.png)

![](img/37752e25380dacd3a400858e09ee6586_205.png)

![](img/37752e25380dacd3a400858e09ee6586_206.png)

我们还可以利用差集求一个事件的**补集**（不在该事件中的结果）：

![](img/37752e25380dacd3a400858e09ee6586_208.png)

![](img/37752e25380dacd3a400858e09ee6586_210.png)

```r
# 事件A（红桃）的补集，即所有非红桃的牌
setdiff(S, A)
```

![](img/37752e25380dacd3a400858e09ee6586_212.png)

## 构建概率空间与计算概率

![](img/37752e25380dacd3a400858e09ee6586_214.png)

概率空间不仅包含样本空间，还包含每个结果对应的概率。

![](img/37752e25380dacd3a400858e09ee6586_216.png)

![](img/37752e25380dacd3a400858e09ee6586_217.png)

![](img/37752e25380dacd3a400858e09ee6586_219.png)

### 等可能结果

![](img/37752e25380dacd3a400858e09ee6586_221.png)

![](img/37752e25380dacd3a400858e09ee6586_222.png)

对于像均匀骰子这样的实验，每个结果概率相等。`prob`包可以自动处理：

![](img/37752e25380dacd3a400858e09ee6586_224.png)

```r
# 方法1：使用probspace函数明确指定概率
S_die <- 1:6
P <- rep(1/6, times = 6)
prob_space1 <- probspace(S_die, probs = P)

![](img/37752e25380dacd3a400858e09ee6586_226.png)

![](img/37752e25380dacd3a400858e09ee6586_228.png)

# 方法2：直接使用rolldie并设置makespace=TRUE，这是最简洁的方式
prob_space2 <- rolldie(times = 1, makespace = TRUE)
prob_space2
```

![](img/37752e25380dacd3a400858e09ee6586_230.png)

![](img/37752e25380dacd3a400858e09ee6586_232.png)

### 非等可能结果

![](img/37752e25380dacd3a400858e09ee6586_234.png)

![](img/37752e25380dacd3a400858e09ee6586_236.png)

对于非均匀的硬币，我们需要指定每个结果的概率：

![](img/37752e25380dacd3a400858e09ee6586_238.png)

![](img/37752e25380dacd3a400858e09ee6586_239.png)

![](img/37752e25380dacd3a400858e09ee6586_241.png)

![](img/37752e25380dacd3a400858e09ee6586_242.png)

```r
# 创建一个不公平的硬币，正面朝上概率0.7，反面0.3
unfair_coin <- tosscoin(times = 1, makespace = TRUE)
probs(unfair_coin) <- c(0.7, 0.3)
unfair_coin

![](img/37752e25380dacd3a400858e09ee6586_244.png)

![](img/37752e25380dacd3a400858e09ee6586_245.png)

![](img/37752e25380dacd3a400858e09ee6586_247.png)

![](img/37752e25380dacd3a400858e09ee6586_249.png)

![](img/37752e25380dacd3a400858e09ee6586_251.png)

# 或者使用iidspace函数直接创建（例如抛三次这种不公平硬币）
iidspace(c("H", "T"), ntrials = 3, probs = c(0.7, 0.3))
```

![](img/37752e25380dacd3a400858e09ee6586_253.png)

![](img/37752e25380dacd3a400858e09ee6586_255.png)

![](img/37752e25380dacd3a400858e09ee6586_257.png)

![](img/37752e25380dacd3a400858e09ee6586_259.png)

### 计算事件概率

![](img/37752e25380dacd3a400858e09ee6586_261.png)

![](img/37752e25380dacd3a400858e09ee6586_262.png)

![](img/37752e25380dacd3a400858e09ee6586_264.png)

现在，我们通过两个例子来学习如何计算具体事件的概率。

![](img/37752e25380dacd3a400858e09ee6586_266.png)

![](img/37752e25380dacd3a400858e09ee6586_267.png)

![](img/37752e25380dacd3a400858e09ee6586_268.png)

![](img/37752e25380dacd3a400858e09ee6586_269.png)

![](img/37752e25380dacd3a400858e09ee6586_271.png)

**例1：掷两个骰子，点数和为7的概率。**

![](img/37752e25380dacd3a400858e09ee6586_273.png)

![](img/37752e25380dacd3a400858e09ee6586_274.png)

![](img/37752e25380dacd3a400858e09ee6586_276.png)

首先建立两个均匀骰子的概率空间：

![](img/37752e25380dacd3a400858e09ee6586_278.png)

![](img/37752e25380dacd3a400858e09ee6586_280.png)

![](img/37752e25380dacd3a400858e09ee6586_281.png)

```r
S_two_dice <- rolldie(times = 2, makespace = TRUE)
```

![](img/37752e25380dacd3a400858e09ee6586_283.png)

![](img/37752e25380dacd3a400858e09ee6586_285.png)

然后，找出点数和为7的所有结果：

![](img/37752e25380dacd3a400858e09ee6586_287.png)

![](img/37752e25380dacd3a400858e09ee6586_289.png)

![](img/37752e25380dacd3a400858e09ee6586_291.png)

```r
event_sum7 <- subset(S_two_dice, X1 + X2 == 7)
```

![](img/37752e25380dacd3a400858e09ee6586_293.png)

![](img/37752e25380dacd3a400858e09ee6586_295.png)

最后，计算概率。有两种等价方法：
1.  对事件中所有结果的概率求和。
2.  用事件的结果数除以样本空间的结果总数。

![](img/37752e25380dacd3a400858e09ee6586_297.png)

![](img/37752e25380dacd3a400858e09ee6586_299.png)

![](img/37752e25380dacd3a400858e09ee6586_300.png)

![](img/37752e25380dacd3a400858e09ee6586_302.png)

```r
# 方法1：概率求和
sum(event_sum7$probs)

![](img/37752e25380dacd3a400858e09ee6586_304.png)

![](img/37752e25380dacd3a400858e09ee6586_306.png)

![](img/37752e25380dacd3a400858e09ee6586_308.png)

![](img/37752e25380dacd3a400858e09ee6586_310.png)

# 方法2：计数法
nrow(event_sum7) / nrow(S_two_dice)

![](img/37752e25380dacd3a400858e09ee6586_312.png)

![](img/37752e25380dacd3a400858e09ee6586_314.png)

![](img/37752e25380dacd3a400858e09ee6586_316.png)

![](img/37752e25380dacd3a400858e09ee6586_318.png)

# 方法3：使用prob函数（最直接）
prob(S_two_dice, event = X1 + X2 == 7)
```
三种方法都会得到相同的结果：**`1/6 ≈ 0.1667`**。

![](img/37752e25380dacd3a400858e09ee6586_320.png)

![](img/37752e25380dacd3a400858e09ee6586_321.png)

![](img/37752e25380dacd3a400858e09ee6586_323.png)

**例2：掷八个骰子，点数和为26的概率。**

![](img/37752e25380dacd3a400858e09ee6586_324.png)

![](img/37752e25380dacd3a400858e09ee6586_326.png)

![](img/37752e25380dacd3a400858e09ee6586_328.png)

这个例子手动计算几乎不可能，但用R则很简单。样本空间非常巨大（6⁸ = 1,679,616种可能），但R可以高效处理。

![](img/37752e25380dacd3a400858e09ee6586_330.png)

![](img/37752e25380dacd3a400858e09ee6586_331.png)

![](img/37752e25380dacd3a400858e09ee6586_332.png)

![](img/37752e25380dacd3a400858e09ee6586_334.png)

![](img/37752e25380dacd3a400858e09ee6586_336.png)

```r
S_eight_dice <- rolldie(times = 8, makespace = TRUE)
event_sum26 <- subset(S_eight_dice, X1 + X2 + X3 + X4 + X5 + X6 + X7 + X8 == 26)
prob(S_eight_dice, event = X1 + X2 + X3 + X4 + X5 + X6 + X7 + X8 == 26)
```
计算得到的概率约为**`0.0748`**。

![](img/37752e25380dacd3a400858e09ee6586_338.png)

![](img/37752e25380dacd3a400858e09ee6586_340.png)

## 总结 🎯

在本教程中，我们一起学习了使用R语言进行概率探索的基本技能。我们从加载必要的工具开始，然后学习了如何定义各种实验的样本空间，包括简单的列表、模拟抽样以及使用专门的`prob`包。接着，我们探讨了如何在R中对事件进行集合运算，如求并集、交集和差集。最后，我们重点学习了如何构建概率空间（包括等可能和非等可能结果），并通过实际例子演示了计算特定事件概率的多种方法。

![](img/37752e25380dacd3a400858e09ee6586_342.png)

![](img/37752e25380dacd3a400858e09ee6586_343.png)

![](img/37752e25380dacd3a400858e09ee6586_344.png)

![](img/37752e25380dacd3a400858e09ee6586_345.png)

![](img/37752e25380dacd3a400858e09ee6586_346.png)

![](img/37752e25380dacd3a400858e09ee6586_347.png)

![](img/37752e25380dacd3a400858e09ee6586_348.png)

![](img/37752e25380dacd3a400858e09ee6586_349.png)

掌握这些技能，你将能够利用R的强大计算能力，解决那些手工计算繁琐甚至不可能完成的概率问题。请务必尝试教程中提到的其他示例，以巩固你的理解。