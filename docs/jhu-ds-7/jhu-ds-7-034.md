# 034：广义线性模型

![](img/04c418ed7f4a37661a27e13d4e6aacab_1.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_2.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_4.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_5.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_6.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_8.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_9.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_11.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_12.png)

在本节课中，我们将学习**广义线性模型**。我们将从之前讨论的线性可加响应模型，转向更广泛的广义线性模型类别。这些模型能够处理线性模型可能难以应对的一些情况，但可能会牺牲线性模型所具有的一些数学上的简洁性。

![](img/04c418ed7f4a37661a27e13d4e6aacab_14.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_16.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_17.png)

在开始讨论广义线性模型之前，我们先回顾一下线性模型，了解其优点和局限性。

![](img/04c418ed7f4a37661a27e13d4e6aacab_19.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_20.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_21.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_22.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_23.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_25.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_26.png)

## 🔍 线性模型的回顾与局限

![](img/04c418ed7f4a37661a27e13d4e6aacab_27.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_29.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_30.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_31.png)

线性模型是应用最广泛的统计技术之一。然而，它并非没有局限性。可加性假设在某些情况下难以应用。

![](img/04c418ed7f4a37661a27e13d4e6aacab_33.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_34.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_35.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_37.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_38.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_39.png)

例如，对于**二元数据**，将其视为可加的会显得很奇怪，其误差结构在这种情况下会变得难以解释。

![](img/04c418ed7f4a37661a27e13d4e6aacab_41.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_42.png)

此外，如果数据是**严格为正**的，那么使用可加的高斯误差会带来问题，因为这允许预测值为负的概率存在。虽然有时这并非大问题，但如果正态分布对负值赋予了很高的正概率，而你的响应变量已知必须为正，那么这对模型来说就是有问题的。

![](img/04c418ed7f4a37661a27e13d4e6aacab_43.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_44.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_45.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_46.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_47.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_48.png)

## 🔄 数据转换的替代方案

![](img/04c418ed7f4a37661a27e13d4e6aacab_50.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_51.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_52.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_53.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_55.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_56.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_58.png)

为了解决上述问题，一种常见的做法是对数据进行转换。

![](img/04c418ed7f4a37661a27e13d4e6aacab_60.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_61.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_62.png)

对于严格为正的结果变量，一个常见的转换是取其**自然对数**。自然对数可能是可解释性最强的转换之一。当然，也存在许多其他转换方法，试图使数据更接近正态分布。

![](img/04c418ed7f4a37661a27e13d4e6aacab_64.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_65.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_66.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_67.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_68.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_69.png)

对于**二项分布数据**，人们常采用所谓的**反正弦平方根变换**，但这通常会严重破坏模型系数的可解释性。

![](img/04c418ed7f4a37661a27e13d4e6aacab_71.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_72.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_73.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_74.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_75.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_76.png)

相比之下，对数变换在很多情况下反而能使系数更具可解释性，我们将单独讨论这一点。

![](img/04c418ed7f4a37661a27e13d4e6aacab_78.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_80.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_82.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_83.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_84.png)

## 🎯 采用广义线性模型的理由

![](img/04c418ed7f4a37661a27e13d4e6aacab_86.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_87.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_89.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_90.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_91.png)

除了对结果变量进行转换或用线性模型近似外，采用广义线性模型还有另一个原因：直接在数据记录的尺度上建立模型，无需转换，这能更好地尊重数据的已知特性。

![](img/04c418ed7f4a37661a27e13d4e6aacab_93.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_94.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_95.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_96.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_97.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_98.png)

如果我们有二元数据，一个真正尊重数据二元性且无需我们进行转换的模型，会显得更加自然和合理。

![](img/04c418ed7f4a37661a27e13d4e6aacab_100.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_101.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_102.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_103.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_104.png)

此外，最常用的自然对数变换不适用于负值或零值。虽然有一些修正方法，但这会损害该变换的一些优良特性，特别是其良好的可解释性。

![](img/04c418ed7f4a37661a27e13d4e6aacab_106.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_108.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_110.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_111.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_112.png)

## 📜 广义线性模型的起源与构成

![](img/04c418ed7f4a37661a27e13d4e6aacab_114.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_115.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_116.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_118.png)

广义线性模型源于1972年Nelder和Wedderburn的一篇著名论文。

![](img/04c418ed7f4a37661a27e13d4e6aacab_119.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_121.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_122.png)

一个广义线性模型包含三个组成部分：

![](img/04c418ed7f4a37661a27e13d4e6aacab_124.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_125.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_126.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_127.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_128.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_129.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_131.png)

1.  **随机成分**：描述随机性的分布必须来自一个特定的分布族，称为**指数族**。这是一个庞大的分布族，包括正态分布、二项分布和泊松分布等。
2.  **系统成分**：即所谓的**线性预测器**。这是我们建模的部分，在线性模型中我们已经非常熟悉。它由回归协变量和系数构成。
3.  **连接函数**：连接函数将指数族分布的重要均值与线性预测器联系起来。

![](img/04c418ed7f4a37661a27e13d4e6aacab_133.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_134.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_135.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_136.png)

因此，我们需要三样东西：一个属于指数族的分布、作为线性预测器的系统成分，以及一个连接两者的连接函数。

![](img/04c418ed7f4a37661a27e13d4e6aacab_138.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_139.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_140.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_141.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_143.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_144.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_146.png)

## 📐 示例一：线性模型作为特例

![](img/04c418ed7f4a37661a27e13d4e6aacab_148.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_149.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_150.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_151.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_152.png)

让我们从一个最熟悉的例子开始：线性模型。

![](img/04c418ed7f4a37661a27e13d4e6aacab_153.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_154.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_156.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_157.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_158.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_159.png)

在这个例子中：
*   **随机成分**：我们假设响应变量 `Y_i` 服从正态分布，均值为 `μ_i`，方差为 `σ^2`。正态分布属于指数族。
*   **系统成分**：线性预测器 `η_i` 定义为协变量 `X_i` 与其系数 `β` 的线性组合。
*   **连接函数**：我们使用**恒等连接函数**，它规定正态分布的均值 `μ_i` 恰好等于线性预测器 `η_i`。

![](img/04c418ed7f4a37661a27e13d4e6aacab_160.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_162.png)

这最终导出了我们一直讨论的线性模型：`Y_i = Σ X_i β + ε_i`。我们只是以另一种方式写出了线性模型：我们没有说误差项服从正态分布，而是说 `Y` 本身服从正态分布（这是前一种设定的结果），并单独指定了线性预测器。

![](img/04c418ed7f4a37661a27e13d4e6aacab_164.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_165.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_166.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_167.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_168.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_169.png)

虽然用可加误差的求和形式写出来似乎更简单，但当我们转向泊松或二项分布等不同设定时，这样做的原因就会变得更加明显。

![](img/04c418ed7f4a37661a27e13d4e6aacab_171.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_172.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_173.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_175.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_176.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_177.png)

## 🪙 示例二：逻辑回归（二项分布）

接下来，我们看看广义线性模型中可能最有用的变体之一：**逻辑回归**。

![](img/04c418ed7f4a37661a27e13d4e6aacab_179.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_180.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_181.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_182.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_183.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_184.png)

在这个设定中，我们的数据是0或1，即**二元数据**。因此，假设它们来自正态分布没有太大意义。自然地，描述抛硬币或0/1结果的唯一可用分布是**伯努利分布**。

![](img/04c418ed7f4a37661a27e13d4e6aacab_186.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_187.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_189.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_191.png)

*   **随机成分**：我们假设结果变量 `Y_i` 服从伯努利分布，其成功概率（即期望值）为 `μ_i`。我们将数据建模为一连串的抛硬币结果，只是每次正面朝上的概率 `μ_i` 可能不同，且不一定等于0.5。
*   **系统成分**：线性预测器 `η_i` 保持不变，仍然是协变量与其系数的线性组合。
*   **连接函数**：在这种情况下，最著名和最常用的是**逻辑连接函数**或**对数几率**。我们通过对几率取自然对数，将均值（正面概率）与线性预测器联系起来。几率定义为 `μ / (1 - μ)`。

这意味着，我们将分布的均值（成功概率）进行转换，然后在这个转换后的尺度上，协变量及其系数（我们线性模型的标准部分）才会出现。

![](img/04c418ed7f4a37661a27e13d4e6aacab_193.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_194.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_195.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_196.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_197.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_198.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_199.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_200.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_201.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_202.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_203.png)

请注意，我们转换的是分布的**均值**，而不是数据 `Y` 本身。这是广义线性模型的一个巧妙之处。我们假设数据来自一个具有特定成功概率的“硬币”，我们以特定方式转换这个概率，使其与我们的协变量和系数相关联。

![](img/04c418ed7f4a37661a27e13d4e6aacab_205.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_207.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_208.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_209.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_211.png)

我们可以通过**逆逻辑函数**（或称Sigmoid函数）从对数几率 `η` 返回到均值 `μ`。这样，我们就可以写出似然函数，并通过最大化这个似然函数来获得参数估计。

![](img/04c418ed7f4a37661a27e13d4e6aacab_212.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_214.png)

## 🔢 示例三：泊松回归

![](img/04c418ed7f4a37661a27e13d4e6aacab_216.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_217.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_218.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_219.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_220.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_221.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_222.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_223.png)

另一个重要例子是**泊松回归**。

![](img/04c418ed7f4a37661a27e13d4e6aacab_225.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_226.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_227.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_228.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_229.png)

*   **随机成分**：假设 `Y_i` 服从泊松分布，均值为 `μ_i`，且 `μ_i > 0`。泊松分布非常适合对**计数数据**建模，这些计数是正的且无上限的（不像二项分布计数受试验次数限制）。
*   **系统成分**：线性预测器 `η_i` 与之前相同。
*   **连接函数**：泊松回归中最常用的连接函数是**对数连接函数**。我们通过对均值 `μ` 取自然对数，将其与线性预测器 `η` 联系起来。同样，我们是对分布的均值取对数，而不是对数据本身取对数。反过来，我们可以通过对 `η` 取指数来回到 `μ`。

![](img/04c418ed7f4a37661a27e13d4e6aacab_231.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_232.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_234.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_235.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_236.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_238.png)

同样，我们可以写出似然函数，并通过最大化似然函数来获得参数估计。

![](img/04c418ed7f4a37661a27e13d4e6aacab_240.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_242.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_243.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_244.png)

## ⚙️ 模型拟合与推断

![](img/04c418ed7f4a37661a27e13d4e6aacab_246.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_247.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_248.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_250.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_251.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_252.png)

广义线性模型的参数估计通过最大化似然函数获得。其求解过程与最小二乘法有相似之处，但形式上更复杂一些，涉及权重和方差项。不过，对于大多数应用者来说，具体的拟合细节是透明的，我们更关心的是模型的解释。

![](img/04c418ed7f4a37661a27e13d4e6aacab_254.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_255.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_257.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_258.png)

与线性模型不同，广义线性模型的方程需要通过**迭代算法**求解。这意味着有时程序可能会失败（例如，在逻辑回归中数据全为0或全为1时）。除此之外，大部分分析对我们来说应该是熟悉的。

![](img/04c418ed7f4a37661a27e13d4e6aacab_260.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_261.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_262.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_263.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_264.png)

*   **预测响应值**：使用估计的系数 `β_hat` 乘以回归变量，得到预测响应值。但请注意，对于逻辑回归，这是在**对数几率尺度**上；对于泊松回归，这是在**对数尺度**上。如果需要回到原始数据的尺度，需要进行相应的逆转换（例如，逻辑回归用逆逻辑函数，泊松回归取指数）。
*   **系数解释**：系数的解释方式与线性回归类似，表示在保持其他变量不变的情况下，该变量每单位变化所引起的**期望响应的变化**。唯一的区别是，这种解释是在**线性预测器的尺度**上进行的（逻辑回归是对数几率尺度，泊松回归是对数均值尺度）。虽然解释稍复杂，但我们获得了在数据原始尺度上建模的好处，且无需转换结果变量。
*   **统计推断**：我们失去了线性模型中那种基于t分布的简洁的封闭形式推断。但广义线性模型的推断在很大程度上是类似的，统计学家已经推导出检验系数显著性（如P值）所需的近似分布。需要注意的是，这些结果基于**大样本渐近理论**，因此需要较大的样本量。如果样本量很小，P值等可能不够可靠。

## ⚠️ 方差结构与过度离散

![](img/04c418ed7f4a37661a27e13d4e6aacab_266.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_267.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_268.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_269.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_270.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_271.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_272.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_273.png)

线性模型有一个**常数方差**的假设。然而，对于广义线性模型，情况有所不同：
*   **伯努利分布**：一个硬币翻转的方差是 `p(1-p)`，即 `μ(1-μ)`。由于 `μ` 随观测点 `i` 变化，方差也随之变化。
*   **泊松分布**：泊松分布的方差等于其均值 `μ`，因此方差也随 `i` 不同而不同。

![](img/04c418ed7f4a37661a27e13d4e6aacab_274.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_275.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_276.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_277.png)

这是一个建模假设，可以进行检查。例如，如果你的数据不符合这种均值-方差关系（例如，泊松数据的观测方差远大于其均值），就会产生问题，这被称为**过度离散**。

![](img/04c418ed7f4a37661a27e13d4e6aacab_279.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_280.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_281.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_282.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_283.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_284.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_285.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_286.png)

为了解决这个问题，可以使用更灵活的方差模型，即使这会失去广义线性模型的一些严格假设。在R等统计软件中，这通常通过“拟”家族来实现（例如 `quasipoisson`, `quasibinomial`）。它们提供了更灵活的方差结构，是处理过度离散的标准选项。

![](img/04c418ed7f4a37661a27e13d4e6aacab_287.png)

## 📝 总结

![](img/04c418ed7f4a37661a27e13d4e6aacab_289.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_290.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_291.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_292.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_293.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_294.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_295.png)

本节课我们一起学习了**广义线性模型**的核心概念。我们了解到，GLM通过三个核心部分——属于指数族的随机成分、线性预测器构成的系统成分以及连接两者的连接函数——扩展了线性模型，使其能够直接处理非正态分布的响应变量（如二元数据、计数数据）。

![](img/04c418ed7f4a37661a27e13d4e6aacab_296.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_297.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_298.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_299.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_300.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_302.png)

我们重点回顾了线性模型的局限性，探讨了采用GLM而非简单数据转换的理由，并通过线性模型、逻辑回归和泊松回归三个具体例子，详细阐述了GLM的构成与应用。我们还简要介绍了GLM的模型拟合、推断、预测解释以及需要注意的方差结构问题。

![](img/04c418ed7f4a37661a27e13d4e6aacab_304.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_305.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_306.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_307.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_308.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_309.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_310.png)

在接下来的课程中，我们将深入探讨两个最重要的具体案例：用于二元结果的**逻辑回归**和用于计数数据的**泊松回归**。