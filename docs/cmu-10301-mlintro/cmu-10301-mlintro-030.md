# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p30 Recitation_8_Reinforcement_Learning.zh_en -BV1Z2cUefE4A_p30-

![](img/8d2cca3c5534b005ac089cc8e60ce85f_1.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_3.png)

## 强化学习基础

![](img/8d2cca3c5534b005ac089cc8e60ce85f_5.png)

在本节课中，我们将学习强化学习的基础概念，包括马尔可夫决策过程（MDP）、策略函数、价值函数和Q函数。

### 马尔可夫决策过程（MDP）

![](img/8d2cca3c5534b005ac089cc8e60ce85f_7.png)

**定义**：马尔可夫决策过程是一个六元组，表示为 (S, A, T, R, γ, S0)，其中：

![](img/8d2cca3c5534b005ac089cc8e60ce85f_9.png)

* **S**：状态集合，表示系统可能处于的所有状态。
* **A**：动作集合，表示在给定状态下可以执行的所有动作。
* **T**：转移函数，表示从状态 S 执行动作 A 后转移到状态 S' 的概率。
* **R**：奖励函数，表示在状态 S 执行动作 A 后获得的奖励。
* **γ**：折扣因子，表示对未来奖励的折现。
* **S0**：初始状态。

![](img/8d2cca3c5534b005ac089cc8e60ce85f_11.png)

**公式**：

```
T(s, a, s') = P(s' | s, a)
R(s, a, s') = reward
```

![](img/8d2cca3c5534b005ac089cc8e60ce85f_13.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_15.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_17.png)

### 策略函数

**定义**：策略函数 π：S → A，表示在给定状态下应该执行的动作。

![](img/8d2cca3c5534b005ac089cc8e60ce85f_19.png)

**公式**：

![](img/8d2cca3c5534b005ac089cc8e60ce85f_21.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_23.png)

```
π(s) = argmax_a R(s, a, π(s))
```

![](img/8d2cca3c5534b005ac089cc8e60ce85f_25.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_27.png)

### 价值函数

**定义**：价值函数 V(s) 表示在状态 s 下按照策略 π 获得的期望回报。

**公式**：

![](img/8d2cca3c5534b005ac089cc8e60ce85f_29.png)

```
V(s) = E[Σ_{t=0}^∞ γ^t R(s_t, a_t, s_{t+1}) | s_0 = s, π]
```

### Q函数

![](img/8d2cca3c5534b005ac089cc8e60ce85f_31.png)

**定义**：Q函数 Q(s, a) 表示在状态 s 下执行动作 a 后获得的期望回报。

![](img/8d2cca3c5534b005ac089cc8e60ce85f_33.png)

**公式**：

```
Q(s, a) = E[R(s, a, s') + γ V(s') | s_0 = s, a_0 = a]
```

![](img/8d2cca3c5534b005ac089cc8e60ce85f_35.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_37.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_39.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_41.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_43.png)

## 价值迭代

![](img/8d2cca3c5534b005ac089cc8e60ce85f_44.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_46.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_47.png)

价值迭代是一种用于计算价值函数的方法，它通过迭代更新每个状态的价值。

**公式**：

```
V_{t+1}(s) = max_a [R(s, a, s') + γ V_t(s')]
```

## Q学习

Q学习是一种基于值迭代的方法，它通过迭代更新每个状态-动作对的Q值。

![](img/8d2cca3c5534b005ac089cc8e60ce85f_49.png)

**公式**：

![](img/8d2cca3c5534b005ac089cc8e60ce85f_51.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_53.png)

```
Q_{t+1}(s, a) = α [R(s, a, s') + γ max_{a'} Q_t(s', a') + (1 - α) Q_t(s, a)]
```

![](img/8d2cca3c5534b005ac089cc8e60ce85f_55.png)

## 总结

![](img/8d2cca3c5534b005ac089cc8e60ce85f_57.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_59.png)

本节课中，我们学习了强化学习的基础概念，包括马尔可夫决策过程、策略函数、价值函数和Q函数。我们还介绍了价值迭代和Q学习两种方法，用于计算价值函数和Q值。

![](img/8d2cca3c5534b005ac089cc8e60ce85f_61.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_63.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_65.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_67.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_69.png)

![](img/8d2cca3c5534b005ac089cc8e60ce85f_71.png)

希望这节课的内容能够帮助您更好地理解强化学习的基础知识。