# 课程 P2：L1.2 - 梯度下降算法 🧠

![](img/a0b313688aaa5693b64432d8cb007a1b_0.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_2.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_4.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_6.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_8.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_9.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_11.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_13.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_15.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_17.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_19.png)

在本节课中，我们将要学习深度学习中的核心优化算法——梯度下降。我们将从基本概念开始，逐步深入到其变种，并解释为什么在深度学习中我们通常使用随机梯度下降及其改进版本。

![](img/a0b313688aaa5693b64432d8cb007a1b_21.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_23.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_25.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_27.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_29.png)

## 概述

![](img/a0b313688aaa5693b64432d8cb007a1b_31.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_33.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_35.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_37.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_39.png)

在机器学习和深度学习中，我们通常有一个需要最小化的目标函数（损失函数）。由于数据集通常非常庞大，直接计算整个数据集的损失函数及其梯度非常昂贵。因此，我们引入了小批量（Mini-batch）的概念，这导致了随机梯度下降算法的诞生。本节课程将详细解释梯度下降的原理、其随机版本以及几种关键的改进算法。

![](img/a0b313688aaa5693b64432d8cb007a1b_41.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_43.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_45.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_47.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_49.png)

## 目标函数与优化

![](img/a0b313688aaa5693b64432d8cb007a1b_51.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_53.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_54.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_56.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_57.png)

在深度学习中，惯例是**最小化**一个损失函数。这有时等价于最大化似然函数。我们的目标是找到模型参数，使得损失函数的值尽可能小。

![](img/a0b313688aaa5693b64432d8cb007a1b_59.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_61.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_63.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_65.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_67.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_68.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_70.png)

然而，损失函数通常基于庞大的数据集计算。评估整个数据集的损失函数及其梯度计算成本非常高。

![](img/a0b313688aaa5693b64432d8cb007a1b_72.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_74.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_75.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_77.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_79.png)

## 小批量与噪声估计

![](img/a0b313688aaa5693b64432d8cb007a1b_81.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_83.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_84.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_86.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_88.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_89.png)

为了解决计算成本问题，在深度学习中，我们使用**小批量**数据。这意味着我们只对数据的一个子集进行求和计算。

![](img/a0b313688aaa5693b64432d8cb007a1b_91.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_93.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_95.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_97.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_99.png)

因此，我们总是只能获得损失函数的一个**噪声估计**。我们用 **J** 来表示这个目标函数的噪声估计。这种噪声通常来源于小批量采样。

![](img/a0b313688aaa5693b64432d8cb007a1b_101.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_103.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_105.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_107.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_108.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_109.png)

由于我们使用的是损失函数的噪声估计，所以我们的梯度也是近似的、随机的。这就是为什么它被称为**随机梯度下降**。

![](img/a0b313688aaa5693b64432d8cb007a1b_111.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_112.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_114.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_116.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_118.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_120.png)

## 梯度下降算法

![](img/a0b313688aaa5693b64432d8cb007a1b_121.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_123.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_125.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_127.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_129.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_130.png)

我们的深度模型由一系列函数（如 f1, f2, ..., fL）组成，这些函数由一系列权重参数化。我们将所有这些参数放在一个列表 **θ** 中。

![](img/a0b313688aaa5693b64432d8cb007a1b_132.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_133.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_135.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_137.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_139.png)

梯度下降的核心思想是沿着损失函数梯度的反方向更新参数，以减小损失值。其更新公式为：

![](img/a0b313688aaa5693b64432d8cb007a1b_141.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_143.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_145.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_147.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_149.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_151.png)

**θ_{t+1} = θ_t - η ∇J(θ_t)**

![](img/a0b313688aaa5693b64432d8cb007a1b_152.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_154.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_156.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_157.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_159.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_160.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_162.png)

其中：
*   **θ_t** 是第 t 次迭代时的参数。
*   **η** 是**学习率**，控制每次更新的步长。
*   **∇J(θ_t)** 是损失函数 J 在 θ_t 处的梯度。

![](img/a0b313688aaa5693b64432d8cb007a1b_163.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_165.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_167.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_169.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_171.png)

由于公式中的负号，我们是在沿着梯度方向**下降**。又因为我们使用的是 J（噪声估计），所以这是**随机**梯度下降。

![](img/a0b313688aaa5693b64432d8cb007a1b_173.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_175.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_177.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_179.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_181.png)

### 关于 J 的进一步说明

![](img/a0b313688aaa5693b64432d8cb007a1b_183.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_185.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_187.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_189.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_191.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_193.png)

J 是目标函数的估计，因为我们只在一小部分数据上训练。例如，在回归问题中使用均方误差（MSE）时，完整的目标函数 F 是在整个数据集上对误差平方求和。

![](img/a0b313688aaa5693b64432d8cb007a1b_195.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_197.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_199.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_201.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_203.png)

而 J 则是在数据集的**一个随机子样本**（即小批量）上的求和。在每次随机梯度下降迭代中，我们都会重新对数据集进行子采样（例如，每次抽取256个数据点），并计算这个小批量上的损失。这就是一个噪声估计。

![](img/a0b313688aaa5693b64432d8cb007a1b_204.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_206.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_207.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_209.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_211.png)

### 为什么使用随机批量？

![](img/a0b313688aaa5693b64432d8cb007a1b_213.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_215.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_217.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_218.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_220.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_222.png)

这里有一个基本假设：数据是**独立同分布** 的。因为数据点相互独立，所以似然函数是每个数据点似然的乘积。取对数后，乘积就变成了求和。为了使小批量能代表整体分布，我们希望样本是**随机**的。

![](img/a0b313688aaa5693b64432d8cb007a1b_224.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_226.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_228.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_230.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_232.png)

当然，也存在一些特例，如**课程学习**，会有意地按难度顺序给模型喂数据，或者进行**难例挖掘**，专注于模型表现不好的困难样本。

![](img/a0b313688aaa5693b64432d8cb007a1b_234.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_235.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_237.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_239.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_241.png)

## 反向传播与计算效率

![](img/a0b313688aaa5693b64432d8cb007a1b_243.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_245.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_247.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_249.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_251.png)

上一节我们介绍了梯度下降的基本思想，本节中我们来看看其高效实现的关键——反向传播。

![](img/a0b313688aaa5693b64432d8cb007a1b_253.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_255.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_257.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_259.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_261.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_263.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_264.png)

假设参数 **θ** 是 d 维的，损失 J 是一个标量值。那么函数 J 是从 d 维空间到一维空间的映射。

![](img/a0b313688aaa5693b64432d8cb007a1b_266.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_267.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_269.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_271.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_272.png)

反向传播的巧妙之处在于，它可以非常高效地计算梯度。计算梯度的成本与进行一次前向传播评估模型的成本相当。只需一次反向传播，就能快速得到梯度向量 **∇J(θ)**。

![](img/a0b313688aaa5693b64432d8cb007a1b_274.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_276.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_278.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_280.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_282.png)

## 为什么只用一阶导数？

![](img/a0b313688aaa5693b64432d8cb007a1b_284.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_286.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_288.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_290.png)

有人可能会问，梯度下降只是沿着梯度方向走一步，这个算法看起来很“笨”。为什么不用更聪明的算法，比如使用二阶导数（海森矩阵）的牛顿法呢？

![](img/a0b313688aaa5693b64432d8cb007a1b_292.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_293.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_295.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_297.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_299.png)

问题在于计算海森矩阵。海森矩阵是一个从 d 维空间到矩阵空间的函数。要计算它，需要进行 d 次反向传播。而深度神经网络的单次前向/反向传播已经非常昂贵，更不用说进行 d 次（d 通常是百万量级）了。

![](img/a0b313688aaa5693b64432d8cb007a1b_301.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_302.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_304.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_306.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_307.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_309.png)

因此，二阶导数和二阶优化算法在深度学习训练中并不适用。我们只能依赖于一阶导数（梯度）。

![](img/a0b313688aaa5693b64432d8cb007a1b_311.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_313.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_315.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_317.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_319.png)

## 梯度下降的改进算法

![](img/a0b313688aaa5693b64432d8cb007a1b_321.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_323.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_325.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_327.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_329.png)

既然我们只能使用一阶导数，那么如何改进基础的梯度下降算法，使其更快、更稳定呢？

![](img/a0b313688aaa5693b64432d8cb007a1b_331.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_333.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_335.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_337.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_339.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_341.png)

### 动量法

![](img/a0b313688aaa5693b64432d8cb007a1b_342.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_344.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_346.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_348.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_350.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_351.png)

动量法的灵感来源于物理学。它引入了一个“速度”变量 **v**，在更新时不仅考虑当前梯度，还保留一部分上一时刻的速度。其更新公式如下：

![](img/a0b313688aaa5693b64432d8cb007a1b_353.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_354.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_356.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_358.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_360.png)

**v_t = γ v_{t-1} + η ∇J(θ_t)**
**θ_{t+1} = θ_t - v_t**

![](img/a0b313688aaa5693b64432d8cb007a1b_362.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_364.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_366.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_368.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_370.png)

其中 **γ** 是动量系数（例如0.9），它保留了之前90%的速度方向。这就像在山谷中滚动一个球，球会由于动量而加速，从而更快地通过平坦区域。动量法可以使梯度下降更快，但也可能因为速度太快而“冲过”最优点。

![](img/a0b313688aaa5693b64432d8cb007a1b_372.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_374.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_375.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_377.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_378.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_380.png)

### Nesterov 加速梯度

![](img/a0b313688aaa5693b64432d8cb007a1b_382.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_384.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_386.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_388.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_390.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_391.png)

Nesterov 加速梯度是对动量法的一种改进，它更加“谨慎”。其思想是：在根据当前动量“展望”一步之后的位置计算梯度，然后用这个“向前看”的梯度来更新。

![](img/a0b313688aaa5693b64432d8cb007a1b_393.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_395.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_397.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_399.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_400.png)

其更新步骤如下：
1.  先进行“展望”：**θ_lookahead = θ_t - γ v_{t-1}**
2.  在展望点计算梯度：**∇J(θ_lookahead)**
3.  用这个梯度更新速度：**v_t = γ v_{t-1} + η ∇J(θ_lookahead)**
4.  更新参数：**θ_{t+1} = θ_t - v_t**

![](img/a0b313688aaa5693b64432d8cb007a1b_402.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_403.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_405.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_407.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_409.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_411.png)

这样，算法在“决定”更新方向之前先“向前看”了一眼，通常能带来更稳定的收敛。

![](img/a0b313688aaa5693b64432d8cb007a1b_413.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_415.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_417.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_419.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_421.png)

## 自适应学习率算法

![](img/a0b313688aaa5693b64432d8cb007a1b_423.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_425.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_427.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_429.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_431.png)

到目前为止，我们讨论的算法都需要手动设置一个固定的学习率 **η**，并通过验证集来调整这个**超参数**（例如使用网格搜索）。这个过程计算成本很高。

![](img/a0b313688aaa5693b64432d8cb007a1b_432.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_434.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_435.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_437.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_439.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_440.png)

因此，人们希望学习率能够**自适应**地调整。以下是几种常见的自适应学习率算法。

![](img/a0b313688aaa5693b64432d8cb007a1b_442.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_444.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_446.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_448.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_450.png)

### AdaGrad

![](img/a0b313688aaa5693b64432d8cb007a1b_452.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_454.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_456.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_458.png)

AdaGrad 试图为每个参数自适应地调整学习率。其核心思想是：累积历史梯度的平方，并用它来缩放当前的学习率。更新公式如下：

![](img/a0b313688aaa5693b64432d8cb007a1b_460.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_462.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_464.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_466.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_467.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_469.png)

**θ_{t+1} = θ_t - (η / √(G_t + ε)) ⊙ g_t**

![](img/a0b313688aaa5693b64432d8cb007a1b_471.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_473.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_475.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_477.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_479.png)

其中：
*   **g_t = ∇J(θ_t)** 是当前梯度。
*   **G_t** 是一个对角矩阵，其对角线元素是截至时间 t 所有历史梯度平方的累加和（即 **G_t = Σ_{τ=1}^{t} g_τ ⊙ g_τ**）。
*   **⊙** 表示逐元素乘法（Hadamard 积）。
*   **ε** 是一个很小的常数（如 1e-8），防止除以零。

![](img/a0b313688aaa5693b64432d8cb007a1b_481.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_482.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_484.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_486.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_488.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_490.png)

这样，经常更新（梯度大）的参数学习率会变小，更新少的参数学习率会相对变大。

![](img/a0b313688aaa5693b64432d8cb007a1b_492.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_493.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_495.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_496.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_498.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_500.png)

**AdaGrad 的问题**：
随着训练进行，**G_t** 中的累加和会越来越大，导致学习率不断衰减，最终可能变得极小，使得优化过程过早停止。

![](img/a0b313688aaa5693b64432d8cb007a1b_502.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_504.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_506.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_508.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_510.png)

### AdaDelta / RMSProp

![](img/a0b313688aaa5693b64432d8cb007a1b_512.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_514.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_516.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_518.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_520.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_522.png)

为了解决 AdaGrad 学习率持续衰减的问题，AdaDelta 和 RMSProp 不再累加全部历史梯度平方，而是使用**指数移动平均**来关注最近一段时间的梯度规模。

![](img/a0b313688aaa5693b64432d8cb007a1b_524.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_526.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_528.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_530.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_532.png)

以下是 RMSProp 的核心思想（AdaDelta 在此基础上还消除了对初始学习率 η 的依赖）：

![](img/a0b313688aaa5693b64432d8cb007a1b_534.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_536.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_538.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_540.png)

**E[g²]_t = γ E[g²]_{t-1} + (1 - γ) g_t ⊙ g_t**
**θ_{t+1} = θ_t - (η / √(E[g²]_t + ε)) ⊙ g_t**

![](img/a0b313688aaa5693b64432d8cb007a1b_542.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_544.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_546.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_548.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_549.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_550.png)

其中 **E[g²]_t** 是梯度平方的指数移动平均值。这样，学习率就能根据最近梯度的幅度自适应调整，而不会无限衰减。

![](img/a0b313688aaa5693b64432d8cb007a1b_552.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_554.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_556.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_558.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_560.png)

## 总结

![](img/a0b313688aaa5693b64432d8cb007a1b_562.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_564.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_565.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_567.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_569.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_571.png)

本节课中我们一起学习了梯度下降算法及其在深度学习中的关键变种。我们从最小化损失函数的目标出发，解释了由于大数据集带来的计算挑战，从而引入了基于小批量的随机梯度下降。我们探讨了反向传播如何高效计算梯度，并分析了在深度学习中主要使用一阶优化方法的原因。

![](img/a0b313688aaa5693b64432d8cb007a1b_573.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_575.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_577.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_579.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_581.png)

![](img/a0b313688aaa5693b64432d8cb007a1b_582.png)

接着，我们介绍了几种重要的改进算法：**动量法**通过引入历史速度来加速收敛；**Nesterov 加速梯度**以更“前瞻”的方式改进了动量法；最后，我们学习了**自适应学习率**算法（如 AdaGrad 和 RMSProp/AdaDelta），它们能够为每个参数自动调整学习率，减少了对手动调参的依赖，并解决了传统 AdaGrad 学习率衰减过快的问题。这些算法构成了现代深度学习优化器的基础。