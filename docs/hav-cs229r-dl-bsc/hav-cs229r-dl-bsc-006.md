# 6：因果性与公平性 🔍⚖️

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_0.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_2.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_4.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_6.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_8.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_10.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_12.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_14.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_16.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_17.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_19.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_21.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_23.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_25.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_26.png)

在本节课中，我们将探讨因果性与公平性这两个重要概念，并理解它们之间的内在联系。我们将从因果性的基本定义和挑战开始，然后转向机器学习中的公平性问题，分析算法决策可能带来的偏见，并讨论如何从因果关系的角度理解和缓解这些偏见。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_28.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_30.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_31.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_33.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_35.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_36.png)

***

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_38.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_39.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_41.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_43.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_44.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_45.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_47.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_49.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_51.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_53.png)

## 概述 📋

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_55.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_57.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_58.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_60.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_62.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_64.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_66.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_68.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_70.png)

本节课分为两个主要部分。首先，我们将学习因果推理的基本框架，理解“相关性不等于因果性”背后的深层原因，并学习如何通过干预和条件控制来估计因果效应。其次，我们将探讨机器学习中的公平性问题，分析算法决策如何产生或加剧社会偏见，并介绍几种衡量和实现公平性的不同方法。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_72.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_74.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_75.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_77.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_78.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_80.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_82.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_84.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_85.png)

***

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_87.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_89.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_91.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_93.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_95.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_97.png)

## 第一部分：因果性

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_99.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_101.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_103.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_105.png)

上一节我们介绍了课程的整体结构，本节中我们来看看因果性的核心概念。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_107.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_109.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_111.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_113.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_115.png)

### 什么是因果性？ 🤔

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_117.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_119.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_121.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_123.png)

人们常说“相关性不等于因果性”，但究竟什么是因果性？在因果理论中，当我们说“A导致B”时，通常意味着A是一种**干预**（我们可以改变世界的某种状态），而B是一种**观察**结果。例如，“吸烟导致肺癌”意味着，如果一个人从不吸烟变为开始吸烟（干预），那么他患肺癌的可能性会增加。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_125.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_127.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_129.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_131.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_133.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_135.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_136.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_138.png)

在形式化研究中，我们假设存在一系列可观测变量（A, B, C, D...），并且我们有能力进行干预，即将某个变量设置为特定值。**相关性**由条件概率 `P(B=b | A=a)` 来刻画，而**因果性**则由干预下的概率 `P(B=b | do(A=a))` 来刻画。直观上，我们可能认为这两者是相同的，但我们将看到事实并非如此。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_140.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_142.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_144.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_146.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_148.png)

### 一个关键例子：运动、体重与心脏病 🏃‍♂️💔

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_150.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_152.png)

为了说明这一点，我们考虑一个假设的例子（请注意，这并非真实的医学建议）。假设我们有三个观测变量：
*   **X**: 是否运动（1=是，0=否）
*   **W**: 是否超重（1=是，0=否）
*   **H**: 是否患有心脏病（1=是，0=否）

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_154.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_156.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_158.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_160.png)

以下是两种可能的因果模型，它们能产生完全相同的观测数据分布，但对干预的反应却截然不同。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_162.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_163.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_165.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_166.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_167.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_169.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_171.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_172.png)

**场景一：运动导致体重变化**
*   运动（X）是初始决定。如果运动（X=1），则一定不超重（W=0）；如果不运动（X=0），则有50%概率超重（W=1）。
*   运动直接影响心脏病：如果运动（X=1），则不得心脏病（H=0）；如果不运动（X=0），则有50%概率得心脏病（H=1）。
*   在这个模型中，**干预“不运动”会影响体重**。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_174.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_175.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_177.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_179.png)

**场景二：体重导致运动选择**
*   体重（W）由基因决定：有25%概率超重（W=1），75%概率不超重（W=0）。
*   体重影响运动选择：如果超重（W=1），则不运动（X=0）；如果不超重（W=0），则以一定概率运动（X=1）。
*   心脏病仍只由运动决定，规则同场景一。
*   在这个模型中，**干预“不运动”不会影响体重**。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_181.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_182.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_184.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_186.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_188.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_189.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_191.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_193.png)

通过精心设置概率参数，可以使这两个模型在**所有观测数据的条件概率上都完全一致**。这意味着，仅通过观察数据，我们无法区分这两个因果模型。然而，如果我们进行干预——例如，强制让一个原本会运动的人不运动——在这两个模型下，此人超重的概率会不同（场景一下为50%，场景二下仍为25%）。这清晰地展示了**条件概率与因果概率之间的区别**。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_195.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_196.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_198.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_199.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_201.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_203.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_204.png)

### 从观测中估计因果效应 🛠️

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_206.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_207.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_209.png)

因果理论的核心目标之一，就是在已知因果图结构但不知具体参数的情况下，从观测数据中估计因果概率 `P(Y=y | do(X=x))`。关键在于控制**混淆变量**。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_211.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_213.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_214.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_216.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_218.png)

**混淆变量**是同时影响原因X和结果Y的变量，它会在X和Y之间制造出一种非因果的关联。例如，在运动（X）、超重（W）和心脏病（H）的例子中，如果真实的因果图是运动同时影响体重和心脏病，而体重和心脏病之间没有直接的因果箭头，那么运动就是一个混淆变量。它使得体重和心脏病在观测上相关，但改变体重并不会导致心脏病风险变化。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_220.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_222.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_223.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_225.png)

为了获得正确的因果效应，我们需要**控制**（或“调整”）混淆变量。以下是调整公式：

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_227.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_229.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_231.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_233.png)

`P(Y=y | do(X=x)) = Σ_z P(Y=y | X=x, Z=z) * P(Z=z)`

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_235.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_237.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_239.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_241.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_243.png)

其中，Z是X在因果图中的所有父节点（即直接影响X的变量集合）。通过条件化Z，我们阻断了X和Y之间所有非因果的“后门路径”，从而可以从观测的条件概率中计算出因果概率。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_245.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_247.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_249.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_251.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_253.png)

### 控制变量的陷阱：对撞偏倚 ⚠️

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_255.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_257.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_259.png)

然而，并非所有变量都适合控制。控制错误的变量，特别是**对撞变量**，反而会引入偏倚。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_261.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_262.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_264.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_266.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_268.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_269.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_271.png)

对撞变量是指由X和Y共同导致的变量Z。例如，假设有两种独立的疾病X和Y，它们都会导致住院（Z）。在整个人群中，X和Y是独立的。但是，如果我们只研究住院人群（即控制Z=1），那么在这个子群体中，X和Y会呈现出**负相关**（因为住院的人必须至少患一种病，如果已知患了Y病，那么他患X病的概率就低于人群基线）。这种在条件化对撞变量后产生的虚假关联称为**对撞偏倚**或**伯克森悖论**。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_273.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_275.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_277.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_279.png)

因此，盲目地控制所有变量并非良策，我们需要基于对因果结构的理解来选择需要控制的变量。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_281.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_283.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_285.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_287.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_289.png)

### 实验设计与工具变量 🧪

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_291.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_293.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_295.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_297.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_299.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_301.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_303.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_304.png)

在理想情况下，我们可以通过**随机对照试验**来直接估计因果效应。例如，在疫苗试验中，通过随机分配疫苗和安慰剂，并确保受试者不知道自己属于哪一组（双盲），我们可以切断“参与试验”这个行为对“是否感染”可能产生的任何非因果影响（即阻断后门路径），从而干净地估计疫苗的效果。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_306.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_308.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_310.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_312.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_314.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_316.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_317.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_319.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_321.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_322.png)

然而，很多时候我们无法进行随机实验。这时，**工具变量** 可以作为一种有用的方法。工具变量Z需要满足两个条件：
1.  Z与处理变量T相关。
2.  Z只能通过影响T来影响结果Y，而不能存在其他路径。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_324.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_326.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_328.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_330.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_331.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_333.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_335.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_337.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_339.png)

如果存在未观测到的混淆因素U同时影响T和Y，但我们可以找到一个工具变量Z，那么我们可以通过以下公式估计处理效应τ：

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_341.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_342.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_344.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_345.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_347.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_349.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_351.png)

`τ = Cov(Z, Y) / Cov(Z, T)`

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_353.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_355.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_357.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_359.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_361.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_362.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_364.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_366.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_368.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_370.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_372.png)

这使我们能够在存在未观测混淆的情况下，依然估计出T对Y的因果效应。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_374.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_376.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_377.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_379.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_381.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_383.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_385.png)

***

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_387.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_389.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_391.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_393.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_395.png)

## 第二部分：公平性

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_397.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_398.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_399.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_401.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_403.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_405.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_406.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_408.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_410.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_412.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_414.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_416.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_418.png)

上一节我们介绍了因果推理的基本工具，本节中我们来看看如何将这些概念应用于理解和解决机器学习中的公平性问题。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_419.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_421.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_422.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_424.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_425.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_427.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_429.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_431.png)

### 算法公平性的挑战 🚨

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_433.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_435.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_437.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_438.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_440.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_442.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_443.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_445.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_446.png)

机器学习算法在许多领域表现出色，甚至超越人类。但一个关键问题是：它们是否对所有人都同样“好”？现实中出现了一些引人注目的公平性案例：
*   **COMPAS再犯风险评估**：被美国一些法院用于保释和量刑决策。分析发现，在未再犯的被告中，黑人被标记为“高风险”的比例远高于白人；而在再犯者中，白人被标记为“低风险”的比例又远高于黑人。
*   **商业性别识别系统**：在一项研究中，系统对白人男性的识别准确率高达99.7%，而对黑人女性的识别准确率仅为65.3%。
*   **简历筛选实验**：研究发现，仅将简历上的名字从黑人常见名改为白人常见名，收到面试回调的几率就增加了50%。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_448.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_450.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_451.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_453.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_455.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_457.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_459.png)

这些偏见并非算法独有，它们深深植根于社会和历史中。但算法的规模化应用可能放大这些偏见。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_460.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_462.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_464.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_466.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_468.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_470.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_471.png)

### 公平性的定义：群体公平 ⚖️

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_472.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_474.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_476.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_478.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_480.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_482.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_483.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_485.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_487.png)

要讨论公平，首先需要定义受保护的群体或类别（如种族、性别）。公平性度量通常分为两类：
*   **差别对待**：关注决策过程是否不公平（例如，明确使用种族作为输入）。
*   **差别影响**：关注决策结果是否存在不公平的差异，无论过程如何。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_489.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_491.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_493.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_495.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_497.png)

在算法公平性中，有几种常见的**群体公平性**定义：
1.  **人口统计平等**：不同群体获得积极结果（如获得贷款）的比例应相同。公式：`P(Ŷ=1 | A=a) = P(Ŷ=1 | A=b)`。
2.  **机会平等**：对于实际结果应为“积极”的个体（如会偿还贷款的人），他们获得积极预测的比例在不同群体间应相同。公式：`P(Ŷ=1 | Y=1, A=a) = P(Ŷ=1 | Y=1, A=b)`。
3.  **预测校准**：在给定预测分数下，实际结果的比例在不同群体间应相同。例如，被预测为“高风险”的人，其实际再犯概率在黑人群体和白人群体中应该相近。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_499.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_501.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_503.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_505.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_507.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_508.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_510.png)

### 公平性之间的权衡与“色盲”算法的局限 🔄

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_512.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_513.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_515.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_517.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_519.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_521.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_522.png)

一个重要的发现是，上述不同的公平性定义通常是**相互冲突的**，无法同时满足。此外，使用完全“色盲”的算法（即不将受保护属性作为输入）往往无法实现任何意义上的公平。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_524.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_526.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_528.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_530.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_532.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_534.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_535.png)

考虑一个贷款场景，有两个群体：蓝组和橙组。两个群体中会还款的人比例相同，但银行对橙组的预测模型更准确（分数分布更分离）。如果银行单纯追求利润最大化，它会为两个群体设置不同的分数阈值，导致贷款批准率不同（差别对待和差别影响）。如果强制使用相同的阈值（色盲），虽然实现了过程公平，但会导致两个群体的贷款批准率不同（差别影响），或者使模型对其中一个群体的校准性变差。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_537.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_539.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_541.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_543.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_545.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_547.png)

现实世界中的FICO信用评分数据也显示了这一点：如果对所有种族群体使用单一的信用分阈值，会导致批准率差异巨大；如果要实现人口统计平等或机会平等，就必须为不同群体设置不同的阈值。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_549.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_550.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_552.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_554.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_556.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_558.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_560.png)

### COMPAS案例：校准性与公平性的视角差异 👁️

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_562.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_564.png)

这引出了对COMPAS争议的深入分析。批评者（如ProPublica）从**被告视角**出发，计算了“在未再犯者中被误判为高风险的比例”，发现黑人远高于白人，认为这不公平。而算法开发者则从**预测者视角**出发，计算了“被预测为高风险者中实际未再犯的比例”，发现黑人和白人相近，认为算法是“校准”的，因而是公平的。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_566.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_568.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_570.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_572.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_574.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_575.png)

这个案例深刻揭示了：
*   公平性取决于你站在谁的立场。
*   **校准性**（预测者视角）和**机会平等**（被告视角）是两个不同且常常冲突的目标。
*   当一个群体上的预测准确性低于另一个群体时，这种冲突几乎不可避免。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_577.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_578.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_580.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_581.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_583.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_585.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_587.png)

### 因果性与反歧视法 📚

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_589.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_591.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_593.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_595.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_596.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_598.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_600.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_602.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_603.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_605.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_606.png)

因果图有助于理解法律中的歧视案例。著名的“伯克利录取悖论”显示，总体上男性录取率高于女性，但按院系细分后，每个院系女性的录取率反而略高或持平。这是因为女性更多地申请了录取率较低的院系。从因果视角看，性别影响了院系选择，院系选择影响了录取结果。如果认为院系选择是合理的中介变量，那么可以认为录取过程本身没有直接性别歧视。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_608.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_609.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_611.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_613.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_615.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_616.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_618.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_619.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_621.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_622.png)

然而，在另一个历史案例（Griggs v. Duke Power Co.）中，电力公司要求高薪职位必须具备高中学历，这 disproportionately 影响了黑人应聘者。虽然因果结构类似（种族→学历→雇佣），但最高法院裁定，由于该工作本身并不需要高中学历，这个要求构成了对种族的间接歧视（“差别影响”）。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_624.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_626.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_628.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_630.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_632.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_633.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_635.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_637.png)

这说明，统计关联本身不能决定是否存在歧视，必须结合对现实世界因果机制和社会背景的理解。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_639.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_641.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_642.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_644.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_645.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_647.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_648.png)

### 超越技术解决方案：价值判断与社会责任 🌍

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_650.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_652.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_654.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_656.png)

最终，公平性问题不能简化为纯粹的技术问题。机器学习系统从数据中学习，做出预测，并影响世界。这个链条的每一步都嵌入了价值判断：
*   **输入选择**：我们选择测量什么，不测量什么？（例如，用“逮捕数”而非“犯罪数”来预测犯罪）。
*   **输出定义**：我们优化什么目标？（例如，优化医疗成本而非健康结果，可能对低收入群体不利）。
*   **反馈循环**：算法的决策会改变它未来看到的数据（例如，预测性警务导致某些社区巡逻增多，逮捕增加，进而强化了该地区高犯罪的预测）。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_658.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_660.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_662.png)

因此，设计“公平”的算法不仅需要改进模型和数据，更需要我们明确并审视这些嵌入在系统设计中的价值选择。算法并非价值中立，我们必须为其带来的社会影响承担责任。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_664.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_666.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_668.png)

***

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_670.png)

## 总结 🎯

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_672.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_674.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_676.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_677.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_679.png)

在本节课中，我们一起学习了：
1.  **因果推理的基础**：区分了相关性 `P(Y|X)` 与因果性 `P(Y|do(X))`，理解了仅凭观测数据无法识别因果方向，以及如何通过控制混淆变量来估计因果效应。
2.  **因果图的运用**：学习了混淆变量、中介变量和对撞变量的概念，以及何时应该或不应该控制某个变量。
3.  **算法公平性的复杂性**：探讨了多种群体公平性的定义（人口统计平等、机会平等、校准性），并认识到它们常常彼此冲突。
4.  **公平性与因果性的交织**：通过COMPAS等案例，看到公平性争议往往源于不同的因果视角和价值立场。也了解到，法律上的反歧视分析需要考虑因果结构和社会合理性。
5.  **系统的责任**：认识到算法公平性不仅仅是数据或模型的问题，而是贯穿于问题定义、数据收集、目标选择和系统部署全过程的系统性挑战，要求设计者做出明确的价值判断。

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_681.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_682.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_684.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_686.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_688.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_690.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_692.png)

![](img/b8e1eeb69d52226e0f8f3a5404af68aa_694.png)

因果性为我们提供了理解世界干预效果的框架，而公平性则要求我们在设计和部署影响社会的算法时，慎重考虑这些干预所带来的不同后果。将两者结合，是构建更负责任的人工智能的关键一步。