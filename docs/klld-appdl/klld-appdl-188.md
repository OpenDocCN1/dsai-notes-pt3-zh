# 188：L82.3 - 近端策略优化 (PPO) 教程 🚀

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_1.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_2.png)

在本节课中，我们将学习近端策略优化算法。这是一种用于强化学习的策略梯度方法，旨在通过限制策略更新的幅度来稳定训练过程。我们将从策略梯度的基础概念出发，逐步理解PPO的核心思想及其实现方式。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_3.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_4.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_5.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_6.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_7.png)

## 📚 策略梯度方法回顾

上一节我们介绍了连续域中的策略优化。我们仍在进行策略梯度方法的策略优化。

以下是策略梯度方法的快速回顾：你有一个优势估计器，然后进行策略梯度更新。这是对未来期望奖励梯度的无偏估计。梯度公式如下：

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_9.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_10.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_11.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_12.png)

**公式：** `∇J(θ) = E[∇ log π(a|s; θ) * Â]`

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_13.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_14.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_15.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_16.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_17.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_18.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_19.png)

其中，`π` 是你的策略网络，`Â` 是优势函数的估计。在实际操作中，我们会在一个有限的样本批次上进行蒙特卡洛估计。一旦计算出梯度，就可以更新策略。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_20.png)

但在现代软件框架中，我们通常不直接编码梯度。在PyTorch或TensorFlow等框架中，我们只需定义损失函数，框架会自动计算梯度。因此，我们只需写出基于上述梯度的损失函数。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_22.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_23.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_24.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_25.png)

## 🛡️ 信赖域策略优化回顾

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_26.png)

我们之前介绍了信赖域策略优化。快速回顾一下，我们知道KL散度的出现有理论依据。但最终，如果你观察信赖域方法并忽略KL散度项，其目标函数与策略梯度非常相似。

如果我们对以下目标函数关于参数θ求梯度，会得到 `π(θ)/π_old` 的梯度。而梯度的对数形式就是 `π` 的梯度除以 `π`。唯一的区别是，这里使用的是旧的策略 `π_old` 而不是新的策略 `π`。

因此，在目标函数层面，两者非常相似。一旦求梯度，只要策略没有发生太大变化（即相对于 `π_old` 变化不大），这些梯度就会彼此相似。这正是引入KL散度约束的原因——确保策略更新不会偏离旧策略太远。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_28.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_29.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_30.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_31.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_32.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_33.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_34.png)

## 🔄 从TRPO到PPO的动机

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_35.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_36.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_37.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_38.png)

为什么我们要从TRPO转向PPO呢？因为虽然TRPO有坚实的理论基础，但其实现（涉及共轭梯度法和二次约束近似）较为复杂。PPO提出了一种更简单、更实用的方法来达到相似的目标：限制策略更新的幅度。

我们可以将约束条件改写为惩罚项，放入目标函数中。或者，我们可以完全摆脱这个约束，直接关注一个核心思想：我们希望新旧策略的比率 `r(θ) = π(θ)/π_old` 接近1。

## ✂️ PPO的核心：裁剪替代目标函数

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_40.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_41.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_42.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_43.png)

PPO的核心创新在于“裁剪替代目标函数”。其目的是强制策略比率 `r(θ)` 接近1。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_44.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_45.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_46.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_47.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_48.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_49.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_50.png)

以下是其工作原理：

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_51.png)

首先，我们定义概率比率 `r_t(θ) = π_θ(a_t|s_t) / π_θ_old(a_t|s_t)`。当 `θ = θ_old` 时，这个比率为1。

如果我们只使用保守策略迭代的目标函数（称为CPI目标），我们会直接优化 `L^{CPI}(θ) = E_t [ r_t(θ) * Â_t ]`。但这无法保证 `r_t(θ)` 接近1，策略可能会偏离太远。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_53.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_54.png)

PPO的解决方案是进行“裁剪”。我们设定一个区间，例如 `[1-ε, 1+ε]`（ε是一个小参数，如0.2）。如果 `r_t(θ)` 超出了这个区间，我们就将其“裁剪”到区间的边界上。具体来说，我们构造以下目标函数：

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_55.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_56.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_57.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_58.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_59.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_60.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_61.png)

**公式：** `L^{CLIP}(θ) = E_t [ min( r_t(θ) * Â_t, clip(r_t(θ), 1-ε, 1+ε) * Â_t ) ]`

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_62.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_63.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_64.png)

这个设计非常巧妙：
1.  **裁剪**：当比率超出 `[1-ε, 1+ε]` 区间时，梯度项被“裁剪”掉，模型失去了进一步朝该方向更新的激励。
2.  **悲观下界**：我们取“未裁剪项”和“裁剪项”的最小值。由于我们是在做最大化问题，这相当于为目标函数 `L^{CPI}` 提供了一个悲观的下界。最大化这个下界的同时，也移除了比率 `r_t(θ)` 远离1的动机。

## 🧩 完整的PPO目标函数

在实际的PPO算法中，总损失函数通常包含三个部分：

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_66.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_67.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_68.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_69.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_70.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_71.png)

**公式：** `L_t^{PPO}(θ) = E_t [ L_t^{CLIP}(θ) - c1 * L_t^{VF}(θ) + c2 * S[π_θ](s_t) ]`

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_72.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_73.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_74.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_75.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_76.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_77.png)

以下是各部分解释：

*   **`L_t^{CLIP}(θ)`**：上面介绍的裁剪替代目标，用于更新策略。
*   **`L_t^{VF}(θ)`**：价值函数误差项。这是一个回归损失，例如均方误差 `(V_θ(s_t) - V_t^{target})^2`。我们需要估计状态价值 `V` 来计算优势函数 `Â_t`。
*   **`S[π_θ](s_t)`**：策略的熵奖励项。用于鼓励探索，防止策略过早收敛到局部最优。`c1` 和 `c2` 是超参数，用于平衡各项的权重。

## 📊 优势估计的改进

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_79.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_80.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_81.png)

优势函数 `Â_t` 的估计对PPO的性能至关重要。一种常见且有效的方法是使用广义优势估计：

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_82.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_83.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_84.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_85.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_86.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_87.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_88.png)

**公式：** `Â_t = δ_t + (γλ) * δ_{t+1} + (γλ)^2 * δ_{t+2} + ...`
其中，`δ_t = r_t + γ * V(s_{t+1}) - V(s_t)`

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_89.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_90.png)

这里的 `λ` 是一个介于0和1之间的参数，用于在偏差和方差之间进行权衡：
*   当 `λ=1` 时，它等价于使用整个轨迹的蒙特卡洛回报来估计优势，方差高但偏差低。
*   当 `λ=0` 时，它只使用一步的TD误差 `δ_t`，偏差高但方差低。
通过调整 `λ`，我们可以取得一个在偏差和方差之间更好的平衡点，从而得到更优质的优势估计。

## 🏃 PPO算法流程

综上所述，PPO算法的典型流程如下：

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_92.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_93.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_94.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_95.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_96.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_97.png)

1.  使用当前策略 `π_θ_old` 在环境中交互，收集一批轨迹数据。
2.  基于收集的数据，计算每个时间步的优势估计 `Â_t`（通常使用GAE方法）和目标价值 `V_t^{target}`。
3.  在多个epoch中，随机打乱数据并分成小批量，对每个小批量计算总损失 `L_t^{PPO}(θ)`。
4.  通过梯度下降（或上升）优化该损失，更新策略参数 `θ`。
5.  用更新后的策略 `π_θ` 替换旧策略 `π_θ_old`，回到步骤1，重复进行。

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_98.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_99.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_100.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_101.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_102.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_103.png)

PPO的主要贡献在于其简单而有效的裁剪机制，它移除了策略比率 `r_t(θ)` 远离1的更新激励，从而在保证训练稳定性的同时，实现了与TRPO相当甚至更好的性能。

## ✅ 总结

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_105.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_106.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_107.png)

![](img/e8fdcbd328c5e6bcd1676f1f6a187783_108.png)

本节课中，我们一起学习了近端策略优化算法。我们从策略梯度基础出发，回顾了信赖域策略优化的思想，并理解了PPO通过“裁剪替代目标函数”来限制策略更新幅度的核心机制。我们还了解了完整的PPO目标函数包含策略裁剪项、价值函数拟合项和熵奖励项，并介绍了使用广义优势估计来优化优势计算。PPO算法因其实现相对简单、效果稳定，已成为深度强化学习中最主流的算法之一。