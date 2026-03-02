#  069：R语言教程 🎲

在本节课中，我们将通过R语言代码来演示大数定律和中心极限定理。我们将从模拟抛硬币开始，逐步扩展到掷骰子，直观地展示随着试验次数增加，样本均值如何收敛于理论期望，以及样本均值的分布如何趋于正态分布。

![](img/b58469f8788d1efc6f9083a388c759cd_1.png)

## 准备工作 🧹

![](img/b58469f8788d1efc6f9083a388c759cd_3.png)

首先，我们需要清理R的工作环境和图形设备，确保从一个干净的状态开始。

![](img/b58469f8788d1efc6f9083a388c759cd_5.png)

```r
# 清理工作空间
rm(list = ls())
# 清理所有图形
graphics.off()
```

## 模拟抛硬币 🪙

![](img/b58469f8788d1efc6f9083a388c759cd_7.png)

上一节我们完成了环境准备，本节中我们来看看如何模拟一个公平的抛硬币过程。我们将创建一个函数来模拟多次抛硬币，并计算其累积均值。

![](img/b58469f8788d1efc6f9083a388c759cd_9.png)

![](img/b58469f8788d1efc6f9083a388c759cd_11.png)

以下是创建 `toss_coin` 函数的步骤：

![](img/b58469f8788d1efc6f9083a388c759cd_13.png)

![](img/b58469f8788d1efc6f9083a388c759cd_15.png)

1.  使用 `sample` 函数进行随机抽样，模拟抛硬币的结果（0代表反面，1代表正面）。
2.  参数 `n` 指定试验次数，`p` 指定正面朝上的概率。
3.  计算每次试验后的累积正面次数，再除以试验次数，得到累积均值。
4.  函数最终返回一个包含试验索引和累积均值的数据框。

![](img/b58469f8788d1efc6f9083a388c759cd_17.png)

```r
toss_coin <- function(n = 30, p = 0.5) {
  # 模拟n次伯努利试验（抛硬币）
  flips <- sample(c(0, 1), size = n, replace = TRUE, prob = c(1-p, p))
  # 计算累积和
  cumulative_sum <- cumsum(flips)
  # 创建索引：1, 2, 3, ..., n
  index <- 1:n
  # 计算累积均值：累积和 / 索引
  cumulative_mean <- cumulative_sum / index
  # 返回包含索引和累积均值的数据框
  return(data.frame(index = index, cumulative_mean = cumulative_mean))
}
```

![](img/b58469f8788d1efc6f9083a388c759cd_19.png)

运行这个函数，我们可以查看一次模拟的结果。

![](img/b58469f8788d1efc6f9083a388c759cd_21.png)

```r
# 模拟30次抛硬币
x <- toss_coin(n=30)
# 查看数据框
print(x)
```

![](img/b58469f8788d1efc6f9083a388c759cd_23.png)

![](img/b58469f8788d1efc6f9083a388c759cd_25.png)

## 可视化抛硬币结果 📊

![](img/b58469f8788d1efc6f9083a388c759cd_26.png)

![](img/b58469f8788d1efc6f9083a388c759cd_28.png)

理解了模拟函数后，我们创建一个绘图函数来直观展示累积均值如何随着试验次数增加而变化。

以下是 `plot_coin_tosses` 函数的核心步骤：

![](img/b58469f8788d1efc6f9083a388c759cd_30.png)

1.  调用 `toss_coin` 函数生成数据。
2.  使用 `ggplot2` 绘制折线图，x轴为试验序号，y轴为累积均值。
3.  添加一条红色水平线表示理论期望值（`p = 0.5`）。
4.  在图中添加文本注释，显示最终的样本均值、期望值和样本量。

```r
library(ggplot2)

![](img/b58469f8788d1efc6f9083a388c759cd_32.png)

plot_coin_tosses <- function(n=30, p=0.5) {
  # 获取抛硬币数据
  coin_tosses <- toss_coin(n, p)
  # 计算最终的样本均值
  last_mean <- tail(coin_tosses$cumulative_mean, 1)
  # 创建图形
  p <- ggplot(coin_tosses, aes(x = index, y = cumulative_mean)) +
    geom_line(color = "blue", size = 1) + # 绘制累积均值曲线
    geom_hline(yintercept = p, color = "red", size = 1, linetype = "dashed") + # 理论期望线
    ylim(0.25, 0.75) + # 设置y轴范围
    labs(x = "试验次数 (Index)", y = "累积均值 (Cumulative Mean)",
         title = paste(n, "次抛硬币的累积均值")) +
    theme_minimal()
  # 添加文本注释
  p <- p + annotate("text", x = n*0.7, y = 0.7, label = paste("最终均值:", round(last_mean, 3)),
                    color = "darkgreen", size = 5)
  p <- p + annotate("text", x = n*0.7, y = 0.65, label = paste("理论期望:", p),
                    color = "darkgreen", size = 5)
  p <- p + annotate("text", x = n*0.7, y = 0.6, label = paste("样本量 n =", n),
                    color = "darkgreen", size = 5)
  return(p)
}

![](img/b58469f8788d1efc6f9083a388c759cd_34.png)

# 生成并显示图形
plot_coin_tosses(30)
```

多次运行此绘图函数，你会发现：
*   在试验次数很少时，累积均值波动很大。
*   随着试验次数 `n` 的增加，累积均值（蓝线）会越来越稳定地围绕理论期望值（红线，0.5）上下波动，并逐渐向其收敛。这直观地演示了**大数定律**：随着样本量增大，样本均值依概率收敛于总体均值。

![](img/b58469f8788d1efc6f9083a388c759cd_36.png)

![](img/b58469f8788d1efc6f9083a388c759cd_37.png)

![](img/b58469f8788d1efc6f9083a388c759cd_39.png)

## 模拟掷骰子 🎲

![](img/b58469f8788d1efc6f9083a388c759cd_41.png)

看过了抛硬币的例子，我们转向另一个经典随机实验——掷骰子。我们将模拟掷一个或多个六面骰子。

首先，创建一个模拟掷单个骰子的函数。

![](img/b58469f8788d1efc6f9083a388c759cd_43.png)

![](img/b58469f8788d1efc6f9083a388c759cd_44.png)

```r
roll_die <- function(n = 1) {
  # 从1到6中随机抽取n次，模拟掷骰子
  outcome <- sample(1:6, size = n, replace = TRUE)
  return(outcome)
}

# 掷一次骰子
roll_die(1)
# 掷两次骰子
roll_die(2)
```

![](img/b58469f8788d1efc6f9083a388c759cd_46.png)

在许多游戏中，如“双骰儿”（craps），需要掷两个骰子并计算点数之和。我们创建一个函数来模拟这个过程。

```r
roll_dice_craps <- function() {
  # 掷两个骰子并求和
  sum(roll_die(2))
}

# 模拟一次“双骰儿”
roll_dice_craps()
```

## 重复实验与频率分布 📈

为了理解结果的分布，我们需要进行大量重复实验。R中的 `replicate` 函数非常适合完成这个任务。

![](img/b58469f8788d1efc6f9083a388c759cd_48.png)

以下是使用 `replicate` 模拟掷骰子的步骤：

![](img/b58469f8788d1efc6f9083a388c759cd_50.png)

1.  使用 `replicate(times, expr)` 重复执行某个表达式。
2.  用 `table()` 统计各结果出现的频数。
3.  绘制频数分布图，观察形状。

![](img/b58469f8788d1efc6f9083a388c759cd_52.png)

![](img/b58469f8788d1efc6f9083a388c759cd_54.png)

```r
# 重复100次“双骰儿”实验
dice_results <- replicate(100, roll_dice_craps())
# 查看点数2到12出现的频数表
freq_table <- table(dice_results)
print(freq_table)

# 绘制频数分布图
plot(freq_table, main = "100次双骰儿实验点数分布",
     xlab = "点数之和", ylab = "频数", col = "lightblue")
```

![](img/b58469f8788d1efc6f9083a388c759cd_56.png)

![](img/b58469f8788d1efc6f9083a388c759cd_58.png)

现在，让我们将实验次数增加到10,000次，观察分布的变化。

![](img/b58469f8788d1efc6f9083a388c759cd_60.png)

```r
# 重复10,000次“双骰儿”实验
dice_results_large <- replicate(10000, roll_dice_craps())
freq_table_large <- table(dice_results_large)
plot(freq_table_large, main = "10,000次双骰儿实验点数分布",
     xlab = "点数之和", ylab = "频数", col = "lightgreen")
```

![](img/b58469f8788d1efc6f9083a388c759cd_62.png)

![](img/b58469f8788d1efc6f9083a388c759cd_64.png)

对比两次绘图结果，你会发现：
*   实验次数为100时，分布图不规则，有随机波动。
*   实验次数达到10,000时，分布图呈现出清晰的**对称三角形状**（两个骰子点数之和2到12的理论分布形状），结果更加稳定和精确。这再次体现了大数定律。

![](img/b58469f8788d1efc6f9083a388c759cd_66.png)

## 中心极限定理的演示 📉

最后，我们通过一个更系统的模拟来演示统计学中最重要的定理之一——**中心极限定理**。该定理指出，无论原始总体分布形状如何，当从总体中抽取足够多的独立样本并计算其均值时，这些样本均值的分布将近似服从正态分布。

![](img/b58469f8788d1efc6f9083a388c759cd_68.png)

![](img/b58469f8788d1efc6f9083a388c759cd_69.png)

我们将模拟以下过程：多次进行“掷`k`个骰子并求平均”的实验，然后观察这些平均值的分布。

![](img/b58469f8788d1efc6f9083a388c759cd_71.png)

```r
# 设置模拟参数
num_simulations <- 10000  # 模拟实验的次数
sample_sizes <- c(1, 2, 10, 30) # 每次实验掷骰子的数量k

![](img/b58469f8788d1efc6f9083a388c759cd_73.png)

![](img/b58469f8788d1efc6f9083a388c759cd_74.png)

par(mfrow = c(2, 2)) # 将画布分为2x2的子图

![](img/b58469f8788d1efc6f9083a388c759cd_76.png)

![](img/b58469f8788d1efc6f9083a388c759cd_77.png)

![](img/b58469f8788d1efc6f9083a388c759cd_79.png)

![](img/b58469f8788d1efc6f9083a388c759cd_80.png)

for (k in sample_sizes) {
  # 对每次模拟实验：掷k个骰子，计算其平均值
  sample_means <- replicate(num_simulations, mean(roll_die(k)))

  # 绘制样本均值的直方图
  hist(sample_means, breaks = 30, probability = TRUE,
       main = paste("每次掷", k, "个骰子的样本均值分布 (n=", num_simulations, ")", sep=""),
       xlab = "样本均值", col = "lightblue", border = "white")

  # 添加理论正态分布曲线作为参考（根据中心极限定理）
  theoretical_sd <- sqrt((35/12) / k) # 单个骰子方差为35/12
  curve(dnorm(x, mean = 3.5, sd = theoretical_sd), add = TRUE,
        col = "red", lwd = 2)

  # 在图上添加实际均值和理论均值
  abline(v = mean(sample_means), col = "blue", lwd = 2, lty = 2) # 实际样本均值
  abline(v = 3.5, col = "darkgreen", lwd = 2) # 理论总体均值
}

par(mfrow = c(1, 1)) # 恢复为单图模式
```

![](img/b58469f8788d1efc6f9083a388c759cd_82.png)

观察这四张子图，你可以发现：
1.  **k=1**：分布是均匀的（1到6的每个整数概率相等），完全不是正态分布。
2.  **k=2**：分布开始呈现中间高、两边低的形状，类似三角分布。
3.  **k=10**：分布形状已经非常接近钟形的正态分布。
4.  **k=30**：分布几乎是一个完美的正态分布曲线。同时，样本均值的分布范围（x轴宽度）比k=1时窄得多，说明均值估计的**变异性**减小，精度增加。

蓝色虚线（实际样本均值）与绿色实线（理论总体均值3.5）几乎重合，说明估计非常准确。红色曲线是拟合的正态分布，与实际分布高度吻合。

![](img/b58469f8788d1efc6f9083a388c759cd_84.png)

![](img/b58469f8788d1efc6f9083a388c759cd_85.png)

这完美地演示了中心极限定理的两个核心要点：
*   **分布形态**：样本均值的分布随着样本量 `k` 增大而趋于正态分布。
*   **分布参数**：该正态分布的均值等于总体均值（`μ = 3.5`），方差等于总体方差除以样本量（`σ²/k`）。因此，样本量越大，样本均值的分布越集中，估计也越精确。

## 总结 🎯

本节课中我们一起学习了如何用R语言模拟随机实验来验证重要的统计原理：
1.  我们通过 `toss_coin` 函数模拟抛硬币，并观察到随着试验次数增加，**累积样本均值逐渐稳定并收敛于理论概率（0.5）**，直观演示了**大数定律**。
2.  我们通过 `roll_die` 和 `replicate` 函数模拟掷骰子，发现大量重复实验后，结果的**频率分布会稳定在理论概率附近**。
3.  我们通过系统模拟不同样本量下骰子平均点数的分布，清晰地展示了**中心极限定理**：无论单次掷骰子的均匀分布形态如何，当计算多次掷骰的平均值时，只要样本量足够大（例如30），这些**平均值的分布就会接近正态分布**，且其波动范围随样本量增大而缩小。

![](img/b58469f8788d1efc6f9083a388c759cd_87.png)

这些模拟实验强化了一个关键观念：在统计分析中，即使我们不知道数据背后的精确分布，只要能够获取足够多的独立样本，就可以利用样本均值的正态性质进行有效的统计推断。这正是许多统计方法（如参数估计、假设检验）的理论基石。