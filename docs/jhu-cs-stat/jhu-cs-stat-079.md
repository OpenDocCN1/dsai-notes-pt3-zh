#  079：使用R分析马尔可夫链教程 🌧️☀️☁️

![](img/da0b05abf2a3bf634634f0f0ac840150_0.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_2.png)

在本节课中，我们将学习如何使用R语言来分析和研究马尔可夫链。我们将展示如何创建马尔可夫链，以及如何回答关于特定随机过程的问题。

![](img/da0b05abf2a3bf634634f0f0ac840150_4.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_6.png)

## 准备工作 🛠️

![](img/da0b05abf2a3bf634634f0f0ac840150_7.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_9.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_10.png)

首先，需要确保清理工作环境。这包括清除所有变量和图形。

![](img/da0b05abf2a3bf634634f0f0ac840150_12.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_14.png)

```r
# 清除环境变量
rm(list = ls())
# 清除所有图形
graphics.off()
```

![](img/da0b05abf2a3bf634634f0f0ac840150_15.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_17.png)

接下来，加载统计工具包。Stat tools工具包非常有用，因为它预装了分析所需的各种包。

![](img/da0b05abf2a3bf634634f0f0ac840150_19.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_21.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_22.png)

```r
# 加载统计工具包
library(stat_tools)
```

![](img/da0b05abf2a3bf634634f0f0ac840150_24.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_26.png)

## 构建马尔可夫链示例 🌤️

![](img/da0b05abf2a3bf634634f0f0ac840150_28.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_29.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_31.png)

我们将使用视频讲座中开发的一个关于天气的问题作为示例。这个例子假设明天的天气只取决于今天的天气。

![](img/da0b05abf2a3bf634634f0f0ac840150_33.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_34.png)

首先，定义马尔可夫链的状态。我们有三个状态：晴天、雨天、阴天。

```r
# 定义状态
states <- c("sunny", "rainy", "cloudy")
```

![](img/da0b05abf2a3bf634634f0f0ac840150_36.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_37.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_38.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_39.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_40.png)

然后，使用`matrix`函数构建转移概率矩阵。这个矩阵与我们在问题中使用的保持一致。

![](img/da0b05abf2a3bf634634f0f0ac840150_42.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_44.png)

```r
# 构建转移概率矩阵
TM <- matrix(c(0.5, 0.4, 0.1,
               0.3, 0.4, 0.3,
               0.2, 0.3, 0.5),
             nrow = 3, byrow = TRUE,
             dimnames = list(states, states))
```

![](img/da0b05abf2a3bf634634f0f0ac840150_45.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_46.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_48.png)

在构建矩阵时，个人偏好是将来源状态放在左侧，目标状态放在右侧。这意味着“我从哪里来”和“我到哪里去”。

![](img/da0b05abf2a3bf634634f0f0ac840150_50.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_52.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_54.png)

## 创建马尔可夫链对象 🔗

![](img/da0b05abf2a3bf634634f0f0ac840150_56.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_58.png)

现在，我们将创建一个新的马尔可夫链对象。这个对象包含转移概率矩阵，并赋予其一个名称。

![](img/da0b05abf2a3bf634634f0f0ac840150_59.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_60.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_62.png)

```r
# 创建马尔可夫链对象
dtmcA <- new("markovchain", transitionMatrix = TM, name = "WeatherChain")
```

![](img/da0b05abf2a3bf634634f0f0ac840150_64.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_65.png)

创建成功后，可以查看该对象的摘要信息，它会告诉你关于这个马尔可夫链的一些基本情况。

![](img/da0b05abf2a3bf634634f0f0ac840150_67.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_68.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_70.png)

```r
# 查看马尔可夫链摘要
summary(dtmcA)
```

![](img/da0b05abf2a3bf634634f0f0ac840150_71.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_73.png)

## 绘制转移图 📊

![](img/da0b05abf2a3bf634634f0f0ac840150_74.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_75.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_77.png)

在回答问题时有帮助的是绘制一个转移图。以下代码来自`diagram`包中的`plotmat`函数，该包在Stat tools中已包含。

![](img/da0b05abf2a3bf634634f0f0ac840150_78.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_80.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_82.png)

```r
# 加载diagram包
library(diagram)

![](img/da0b05abf2a3bf634634f0f0ac840150_84.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_85.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_87.png)

# 绘制转移概率矩阵图
plotmat(t(TM), # 转置矩阵以匹配分析习惯
        name = states,
        lwd = 1,
        box.lwd = 2,
        cex.txt = 0.8,
        box.size = 0.1,
        box.type = "circle",
        box.prop = 0.5,
        arr.length = 0.2,
        arr.width = 0.1,
        self.cex = 0.4,
        self.shiftx = 0.12,
        self.shifty = 0.1)
```

![](img/da0b05abf2a3bf634634f0f0ac840150_89.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_91.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_93.png)

`plotmat`函数是一个纯粹的绘图工具，不进行分析。为了与我们的分析习惯保持一致（来源在左，目标在右），我们对转移矩阵进行了转置。运行代码后，生成的图表应与我们的转移矩阵匹配。例如，从晴天到雨天的箭头概率应为0.4。

![](img/da0b05abf2a3bf634634f0f0ac840150_95.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_97.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_99.png)

## 分析具体问题 ❓

![](img/da0b05abf2a3bf634634f0f0ac840150_101.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_103.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_105.png)

上一节我们创建了马尔可夫链并可视化了转移过程，本节中我们来看看如何用它来回答具体问题。

![](img/da0b05abf2a3bf634634f0f0ac840150_107.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_109.png)

第一个问题是：假设今天是晴天，求未来五天天气依次为“晴天、雨天、阴天、阴天、晴天”的概率。

![](img/da0b05abf2a3bf634634f0f0ac840150_110.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_112.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_114.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_116.png)

这本质上是计算一个特定路径的概率。给定今天是晴天（初始状态W1），我们需要计算一连串转移的概率：

![](img/da0b05abf2a3bf634634f0f0ac840150_118.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_119.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_121.png)

1.  晴天 → 晴天：概率为 **0.5**
2.  晴天 → 雨天：概率为 **0.4**
3.  雨天 → 阴天：概率为 **0.3**
4.  阴天 → 阴天：概率为 **0.5**
5.  阴天 → 晴天：概率为 **0.2**

![](img/da0b05abf2a3bf634634f0f0ac840150_123.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_124.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_125.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_127.png)

总概率是这些转移概率的乘积。

![](img/da0b05abf2a3bf634634f0f0ac840150_129.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_130.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_132.png)

```r
# 计算特定路径的概率
prob_path <- 0.5 * 0.4 * 0.3 * 0.5 * 0.2
prob_path
# 输出应为 0.006
```

![](img/da0b05abf2a3bf634634f0f0ac840150_134.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_136.png)

## 利用查普曼-科尔莫戈罗夫方程 🔢

![](img/da0b05abf2a3bf634634f0f0ac840150_138.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_140.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_141.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_143.png)

我们还可以利用查普曼-科尔莫戈罗夫方程来解决更多问题。例如，我们可以定义初始状态向量（1表示处于该状态，0表示不处于）。

![](img/da0b05abf2a3bf634634f0f0ac840150_144.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_146.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_148.png)

首先，可以查看马尔可夫链的递归状态。

![](img/da0b05abf2a3bf634634f0f0ac840150_150.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_152.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_154.png)

```r
# 查看递归状态
recurrentStates(dtmcA)
```

![](img/da0b05abf2a3bf634634f0f0ac840150_156.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_158.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_160.png)

如果我们想设定初始状态为晴天，则初始状态向量为 `c(1, 0, 0)`。

![](img/da0b05abf2a3bf634634f0f0ac840150_162.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_164.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_166.png)

```r
# 定义初始状态向量（晴天）
initial_state <- c(1, 0, 0)
```

![](img/da0b05abf2a3bf634634f0f0ac840150_168.png)

现在，问题可能是：从今天（晴天）开始，两天后的天气预测如何？

![](img/da0b05abf2a3bf634634f0f0ac840150_170.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_171.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_172.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_173.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_175.png)

这可以通过初始状态向量乘以转移矩阵的2次方（即两天）来计算。

![](img/da0b05abf2a3bf634634f0f0ac840150_177.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_179.png)

```r
# 计算两天后的状态分布
state_after_2days <- initial_state %*% (TM %^% 2)
state_after_2days
```

![](img/da0b05abf2a3bf634634f0f0ac840150_181.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_183.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_185.png)

我们也可以直接对转移矩阵求幂来得到同样的结果。

![](img/da0b05abf2a3bf634634f0f0ac840150_187.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_189.png)

```r
# 直接计算转移矩阵的2次方
TM_2 <- TM %^% 2
TM_2
```

![](img/da0b05abf2a3bf634634f0f0ac840150_191.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_192.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_194.png)

结果显示，两天后有约39%的概率下雨，39%的概率晴天，22%的概率阴天。

![](img/da0b05abf2a3bf634634f0f0ac840150_196.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_198.png)

同样地，我们可以计算四天后的情况。

![](img/da0b05abf2a3bf634634f0f0ac840150_200.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_201.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_202.png)

```r
# 计算四天后的状态分布（从晴天开始）
state_after_4days_from_sunny <- initial_state %*% (TM %^% 4)
state_after_4days_from_sunny

![](img/da0b05abf2a3bf634634f0f0ac840150_204.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_206.png)

# 或者直接查看四步转移矩阵，它包含了所有初始状态的可能性
TM_4 <- TM %^% 4
TM_4
```

![](img/da0b05abf2a3bf634634f0f0ac840150_208.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_210.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_212.png)

通过`TM_4`矩阵，我们可以查看从任何初始状态（晴天、雨天、阴天）出发，四天后的状态分布。

![](img/da0b05abf2a3bf634634f0f0ac840150_214.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_215.png)

## 探索稳态概率 ⚖️

![](img/da0b05abf2a3bf634634f0f0ac840150_217.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_218.png)

如果我们想计算200天甚至2000天后的状态，会发现分布趋于稳定。这个稳定的分布称为**稳态概率**或**极限概率**。

![](img/da0b05abf2a3bf634634f0f0ac840150_220.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_222.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_223.png)

我们可以使用`steadyStates`函数直接计算稳态分布。

![](img/da0b05abf2a3bf634634f0f0ac840150_225.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_226.png)

```r
# 计算稳态概率分布
steady_state <- steadyStates(dtmcA)
steady_state
```

![](img/da0b05abf2a3bf634634f0f0ac840150_228.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_230.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_232.png)

稳态概率分布是一个向量，表示无论从哪个状态开始，经过足够长的时间后，处于各个状态的概率。对于我们的天气模型，稳态概率大约是：雨天37%，晴天33%，阴天29%。这意味着从长期来看，天气的分布与初始状态无关。

![](img/da0b05abf2a3bf634634f0f0ac840150_234.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_235.png)

最后，我们可以将这个稳态概率信息更新到我们的转移图中。

![](img/da0b05abf2a3bf634634f0f0ac840150_237.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_238.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_240.png)

```r
# 重新绘图，可考虑将稳态概率作为注释加入（此处为概念性步骤）
# 实际绘图代码可能需要调整以显示稳态概率，例如在状态框旁添加文本
plotmat(t(TM),
        name = states,
        ... # 其他绘图参数
        )
# 假设我们手动添加文本注释，例如在晴天状态旁添加"33%"
```

![](img/da0b05abf2a3bf634634f0f0ac840150_242.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_244.png)

## 总结 📝

![](img/da0b05abf2a3bf634634f0f0ac840150_246.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_248.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_249.png)

本节课中我们一起学习了如何使用R语言分析和研究马尔可夫链。我们从清理环境和加载工具包开始，逐步构建了一个天气预测的马尔可夫链模型，定义了状态和转移矩阵。我们创建了马尔可夫链对象，并绘制了转移图来可视化过程。通过具体示例，我们计算了特定路径的概率，并利用查普曼-科尔莫戈罗夫方程预测了未来多天的状态分布。最后，我们探讨了马尔可夫链的稳态概率，它揭示了系统长期的行为规律，与初始状态无关。希望这些方法和工具能对您未来的数据分析有所帮助。