# 080：回归模型扩展应用 🚀

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_1.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_2.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_4.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_5.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_6.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_7.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_8.png)

在本节课中，我们将探讨如何将线性模型和广义线性模型扩展到更复杂的场景。我们将学习如何使用回归样条拟合复杂的非线性函数，以及如何利用傅里叶基函数分析声音信号。这些技术展示了线性模型框架的强大和灵活性。

---

## 使用回归样条拟合复杂函数 📈

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_10.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_12.png)

上一节我们介绍了线性模型的基础。本节中我们来看看如何用它来拟合复杂的非线性函数。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_13.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_14.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_16.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_17.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_19.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_20.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_21.png)

我们之前见过通过添加平方项、立方项或多项式项来拟合低阶函数。然而，如果你想拟合一个像正弦曲线这样复杂的函数，该怎么办呢？我们可以将模型指定为 **y = f(x) + ε**，其中 **f** 可能是一个复杂函数。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_23.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_24.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_26.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_27.png)

事实证明，有一种相当简单的方法可以做到这一点，我将向你展示一个简单的第一步。这背后有完整的理论体系，我们只介绍一些基础知识。第一步是使用所谓的**回归样条**。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_29.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_30.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_31.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_33.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_35.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_36.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_38.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_40.png)

我们的模型 **y = f(x) + ε** 可以具体写成：
**y = β₀ + β₁x + Σ [γⱼ (x - κⱼ)₊]**，其中 **j = 1, ..., D**

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_42.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_43.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_44.png)

这里的函数 **(x - κⱼ)₊** 表示：如果括号内的值为正，则返回该值；否则返回零。点 **κ₁, ..., κ_D** 被称为**节点**。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_46.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_47.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_48.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_49.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_50.png)

这个方法的直观想法是：想象一根棍子，你在几个点处“弯曲”它（而不是折断），从而形成一条连续的折线来逼近目标函数。这些节点就是弯曲点。上述数学形式确保了函数是连续的（没有断点）。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_52.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_53.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_54.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_55.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_57.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_59.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_60.png)

以下是使用回归样条的基本步骤：

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_62.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_63.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_64.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_65.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_67.png)

1.  **选择节点**：在自变量的范围内选择一系列点作为节点。
2.  **构造样条项**：对每个节点，计算 **(x - κⱼ)₊**，形成新的预测变量。
3.  **拟合线性模型**：将因变量 **y** 对截距项、线性项 **x** 以及所有样条项进行回归。

通过一个模拟的正弦曲线加噪声数据例子，我们可以看到这种方法能很好地拟合曲线。但一个问题是，在节点处拟合的曲线是连续的，但可能不够平滑（存在“尖角”）。

为了让曲线在节点处也平滑（即一阶导数连续），我们可以使用平方项。改进后的模型是：
**y = β₀ + β₁x + β₂x² + Σ [γⱼ (x - κⱼ)₊²]**，其中 **j = 1, ..., D**

这样，当 **x** 超过节点 **κⱼ** 时，贡献是差值的平方，从而保证了曲线的平滑性。拟合结果会是一条光滑的曲线。

**核心要点**：我们仅仅使用普通的线性回归，通过添加节点和样条项，就拟合出了相当复杂的函数。这组样条项被称为一个**基**，它是构建函数的“积木块”。回归样条是众多基函数中的一种。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_69.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_70.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_72.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_73.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_74.png)

**存在的挑战与进阶方向**：
*   我们需要确定节点的位置和数量。节点太少可能欠拟合，太多可能过拟合。
*   现代解决方案是放置大量节点，并添加一个**正则化项**来惩罚样条项系数的大小，从而控制模型复杂度。
*   这种方法同样可以应用于广义线性模型，只需在线性预测器中指定回归样条即可。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_75.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_76.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_77.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_79.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_81.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_82.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_83.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_85.png)

---

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_87.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_88.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_89.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_90.png)

## 使用傅里叶基进行谐波分析 🎵

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_92.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_93.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_94.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_95.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_97.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_99.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_100.png)

现在，让我们转向另一个有趣的例子，看看如何使用另一种基函数——傅里叶基来分析声音。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_102.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_104.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_105.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_106.png)

设想一个场景：有人连续弹奏了一个和弦（三个音符同时发声），我们录制了这段数字音频。能否让R语言分析这段声音，识别出是哪三个音符呢？

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_108.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_109.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_111.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_112.png)

一个音阶（如C大调：Do, Re, Mi, Fa, Sol, La, Ti, Do）中的每个音符对应一个特定频率。一个和弦由几个特定频率的音符叠加而成。如果我们用正弦波模拟每个音符的声音，将它们相加就得到了和弦的数字化信号。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_114.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_115.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_116.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_117.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_118.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_120.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_121.png)

为了识别和弦，我们可以构建一个**傅里叶基**。思路是：用数据中可能存在的所有音符（例如一个八度内的8个音符）对应的正弦函数作为预测变量，来拟合我们的和弦信号（作为因变量）。模型可以表示为：
**和弦信号 ≈ Σ [αⱼ * sin(频率ⱼ * t)]**，其中 **j** 代表不同音符。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_123.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_124.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_125.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_126.png)

以下是分析步骤：

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_128.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_129.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_130.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_131.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_132.png)

1.  **生成基函数**：为每个可能的音符频率创建正弦波时间序列作为预测变量。
2.  **拟合线性模型**：将录制的和弦信号对这些正弦波基函数进行回归（通常去除截距项）。
3.  **检查系数**：回归系数的大小表明了对应音符在和弦中的存在与否及强度。系数大的音符即被认为是和弦的组成部分。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_134.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_135.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_136.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_137.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_138.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_139.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_140.png)

在示例中，模型正确地识别出了C大调和弦（C、E、G音符）对应的系数显著大于其他音符。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_142.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_143.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_144.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_145.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_146.png)

这仅仅使用了正弦分量。实际上，完整的谐波分析还应包括余弦分量。一种自动拟合所有可能正弦和余弦项的方法被称为**离散傅里叶变换**。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_147.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_148.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_149.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_151.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_153.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_155.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_156.png)

*   DFT本质上就是拟合一个包含所有可能频率的正弦和余弦项的线性模型，模型是完全饱和的（系数数量等于时间点数量）。
*   人们通常使用DFT而不是直接拟合线性模型，是因为统计学家Tukey等人发现了**快速傅里叶变换**算法，它能极其高效地完成DFT计算。
*   声音工程师经常对信号进行FFT并绘制频谱图，这本质上就是在查看一个以大量正弦/余弦项为回归元的线性模型的系数强度。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_158.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_159.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_160.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_161.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_162.png)

---

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_164.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_165.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_166.png)

## 总结与展望 🎯

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_168.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_169.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_170.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_171.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_172.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_173.png)

本节课中我们一起学习了线性模型的两个强大扩展应用。

首先，我们看到了如何使用**回归样条**，仅用几行R代码就能拟合非常复杂的非线性函数。其次，我们探索了如何使用**傅里叶基**和线性模型来完成看似不相关的任务——分析和弦的构成音符。这两者都凸显了线性模型框架的简洁性和强大功能。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_175.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_176.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_177.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_178.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_179.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_180.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_181.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_182.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_183.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_184.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_185.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_186.png)

为了进一步深化你的知识，建议从两个方向继续学习：
1.  **广义线性模型**：我们在课程中仅初步接触，它在处理非正态响应变量（如计数、二元数据）时至关重要。
2.  **纵向数据与多层级模型**：我们的课程假设误差独立。但在许多实际场景中（如重复测量、家族数据），数据之间存在相关性。处理这种相关性是线性模型扩展到更广泛、更重要领域的关键部分。

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_188.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_190.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_191.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_192.png)

![](img/da5f7c3aea23d2a07a4df3a7eaf5a0f0_193.png)

希望你能享受这门课程，并运用所学知识继续探索。数据科学的世界还有很多精彩内容等待发现。