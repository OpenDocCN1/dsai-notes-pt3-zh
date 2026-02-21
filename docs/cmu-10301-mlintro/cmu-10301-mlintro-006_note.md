# 机器学习导论：第6讲：感知器与在线学习 👁️‍🗨️

![](img/223aea760bce52b872e46ca99b14c6fe_0.png)

![](img/223aea760bce52b872e46ca99b14c6fe_2.png)

![](img/223aea760bce52b872e46ca99b14c6fe_3.png)

![](img/223aea760bce52b872e46ca99b14c6fe_4.png)

![](img/223aea760bce52b872e46ca99b14c6fe_5.png)

![](img/223aea760bce52b872e46ca99b14c6fe_6.png)

![](img/223aea760bce52b872e46ca99b14c6fe_7.png)

![](img/223aea760bce52b872e46ca99b14c6fe_9.png)

![](img/223aea760bce52b872e46ca99b14c6fe_10.png)

![](img/223aea760bce52b872e46ca99b14c6fe_12.png)

![](img/223aea760bce52b872e46ca99b14c6fe_14.png)

![](img/223aea760bce52b872e46ca99b14c6fe_16.png)

![](img/223aea760bce52b872e46ca99b14c6fe_17.png)

![](img/223aea760bce52b872e46ca99b14c6fe_18.png)

![](img/223aea760bce52b872e46ca99b14c6fe_19.png)

![](img/223aea760bce52b872e46ca99b14c6fe_21.png)

## 概述

![](img/223aea760bce52b872e46ca99b14c6fe_22.png)

![](img/223aea760bce52b872e46ca99b14c6fe_23.png)

![](img/223aea760bce52b872e46ca99b14c6fe_25.png)

![](img/223aea760bce52b872e46ca99b14c6fe_26.png)

![](img/223aea760bce52b872e46ca99b14c6fe_27.png)

![](img/223aea760bce52b872e46ca99b14c6fe_29.png)

![](img/223aea760bce52b872e46ca99b14c6fe_30.png)

![](img/223aea760bce52b872e46ca99b14c6fe_32.png)

![](img/223aea760bce52b872e46ca99b14c6fe_33.png)

在本节课中，我们将介绍机器学习中的感知器模型，并探讨在线学习这一新的机器学习范式。我们将学习如何使用感知器进行分类，并了解在线学习在现实世界应用中的重要性。

![](img/223aea760bce52b872e46ca99b14c6fe_34.png)

![](img/223aea760bce52b872e46ca99b14c6fe_35.png)

![](img/223aea760bce52b872e46ca99b14c6fe_37.png)

![](img/223aea760bce52b872e46ca99b14c6fe_38.png)

![](img/223aea760bce52b872e46ca99b14c6fe_40.png)

![](img/223aea760bce52b872e46ca99b14c6fe_42.png)

![](img/223aea760bce52b872e46ca99b14c6fe_43.png)

![](img/223aea760bce52b872e46ca99b14c6fe_45.png)

![](img/223aea760bce52b872e46ca99b14c6fe_46.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_47.png)

![](img/223aea760bce52b872e46ca99b14c6fe_49.png)

![](img/223aea760bce52b872e46ca99b14c6fe_50.png)

![](img/223aea760bce52b872e46ca99b14c6fe_52.png)

![](img/223aea760bce52b872e46ca99b14c6fe_54.png)

![](img/223aea760bce52b872e46ca99b14c6fe_55.png)

![](img/223aea760bce52b872e46ca99b14c6fe_57.png)

## 1. 课程回顾 📚

![](img/223aea760bce52b872e46ca99b14c6fe_59.png)

![](img/223aea760bce52b872e46ca99b14c6fe_61.png)

![](img/223aea760bce52b872e46ca99b14c6fe_63.png)

![](img/223aea760bce52b872e46ca99b14c6fe_65.png)

![](img/223aea760bce52b872e46ca99b14c6fe_66.png)

![](img/223aea760bce52b872e46ca99b14c6fe_67.png)

![](img/223aea760bce52b872e46ca99b14c6fe_69.png)

![](img/223aea760bce52b872e46ca99b14c6fe_70.png)

![](img/223aea760bce52b872e46ca99b14c6fe_71.png)

在开始介绍感知器之前，让我们回顾一下之前学过的内容：

![](img/223aea760bce52b872e46ca99b14c6fe_72.png)

![](img/223aea760bce52b872e46ca99b14c6fe_73.png)

![](img/223aea760bce52b872e46ca99b14c6fe_75.png)

![](img/223aea760bce52b872e46ca99b14c6fe_77.png)

![](img/223aea760bce52b872e46ca99b14c6fe_79.png)

![](img/223aea760bce52b872e46ca99b14c6fe_80.png)

![](img/223aea760bce52b872e46ca99b14c6fe_81.png)

![](img/223aea760bce52b872e46ca99b14c6fe_82.png)

*   **线性回归**：使用线性模型预测连续值。
*   **逻辑回归**：使用线性模型进行二分类。
*   **K近邻（KNN）**：基于最近邻的决策规则进行分类。

![](img/223aea760bce52b872e46ca99b14c6fe_84.png)

![](img/223aea760bce52b872e46ca99b14c6fe_85.png)

![](img/223aea760bce52b872e46ca99b14c6fe_86.png)

![](img/223aea760bce52b872e46ca99b14c6fe_87.png)

![](img/223aea760bce52b872e46ca99b14c6fe_89.png)

![](img/223aea760bce52b872e46ca99b14c6fe_91.png)

![](img/223aea760bce52b872e46ca99b14c6fe_93.png)

![](img/223aea760bce52b872e46ca99b14c6fe_95.png)

![](img/223aea760bce52b872e46ca99b14c6fe_96.png)

这些模型为我们理解更复杂的算法奠定了基础。接下来，我们将学习一个更基础但同样重要的线性分类模型——感知器。

![](img/223aea760bce52b872e46ca99b14c6fe_97.png)

![](img/223aea760bce52b872e46ca99b14c6fe_99.png)

![](img/223aea760bce52b872e46ca99b14c6fe_101.png)

![](img/223aea760bce52b872e46ca99b14c6fe_103.png)

![](img/223aea760bce52b872e46ca99b14c6fe_104.png)

![](img/223aea760bce52b872e46ca99b14c6fe_105.png)

![](img/223aea760bce52b872e46ca99b14c6fe_106.png)

![](img/223aea760bce52b872e46ca99b14c6fe_107.png)

![](img/223aea760bce52b872e46ca99b14c6fe_109.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_110.png)

![](img/223aea760bce52b872e46ca99b14c6fe_112.png)

![](img/223aea760bce52b872e46ca99b14c6fe_113.png)

![](img/223aea760bce52b872e46ca99b14c6fe_114.png)

![](img/223aea760bce52b872e46ca99b14c6fe_115.png)

![](img/223aea760bce52b872e46ca99b14c6fe_116.png)

![](img/223aea760bce52b872e46ca99b14c6fe_117.png)

## 2. 感知器模型 🤖

![](img/223aea760bce52b872e46ca99b14c6fe_119.png)

![](img/223aea760bce52b872e46ca99b14c6fe_121.png)

![](img/223aea760bce52b872e46ca99b14c6fe_123.png)

![](img/223aea760bce52b872e46ca99b14c6fe_125.png)

![](img/223aea760bce52b872e46ca99b14c6fe_126.png)

![](img/223aea760bce52b872e46ca99b14c6fe_127.png)

![](img/223aea760bce52b872e46ca99b14c6fe_129.png)

![](img/223aea760bce52b872e46ca99b14c6fe_130.png)

感知器是一种简单的线性二分类模型，它使用线性决策边界来区分不同的类别。其核心思想是找到一个超平面，将不同类别的数据点分开。

![](img/223aea760bce52b872e46ca99b14c6fe_132.png)

![](img/223aea760bce52b872e46ca99b14c6fe_133.png)

![](img/223aea760bce52b872e46ca99b14c6fe_134.png)

![](img/223aea760bce52b872e46ca99b14c6fe_136.png)

![](img/223aea760bce52b872e46ca99b14c6fe_137.png)

![](img/223aea760bce52b872e46ca99b14c6fe_139.png)

![](img/223aea760bce52b872e46ca99b14c6fe_141.png)

![](img/223aea760bce52b872e46ca99b14c6fe_143.png)

![](img/223aea760bce52b872e46ca99b14c6fe_145.png)

其预测公式如下：

![](img/223aea760bce52b872e46ca99b14c6fe_147.png)

![](img/223aea760bce52b872e46ca99b14c6fe_148.png)

![](img/223aea760bce52b872e46ca99b14c6fe_150.png)

![](img/223aea760bce52b872e46ca99b14c6fe_152.png)

![](img/223aea760bce52b872e46ca99b14c6fe_154.png)

![](img/223aea760bce52b872e46ca99b14c6fe_156.png)

![](img/223aea760bce52b872e46ca99b14c6fe_157.png)

![](img/223aea760bce52b872e46ca99b14c6fe_159.png)

**公式**：`y = sign(W^T * x + b)`

![](img/223aea760bce52b872e46ca99b14c6fe_161.png)

![](img/223aea760bce52b872e46ca99b14c6fe_163.png)

![](img/223aea760bce52b872e46ca99b14c6fe_165.png)

![](img/223aea760bce52b872e46ca99b14c6fe_166.png)

![](img/223aea760bce52b872e46ca99b14c6fe_167.png)

![](img/223aea760bce52b872e46ca99b14c6fe_168.png)

![](img/223aea760bce52b872e46ca99b14c6fe_170.png)

![](img/223aea760bce52b872e46ca99b14c6fe_171.png)

其中：
*   `y` 是预测的类别标签（通常为 +1 或 -1）。
*   `W` 是权重向量。
*   `x` 是输入的特征向量。
*   `b` 是偏置项。
*   `sign` 是符号函数，当输入大于等于0时输出+1，否则输出-1。

![](img/223aea760bce52b872e46ca99b14c6fe_172.png)

![](img/223aea760bce52b872e46ca99b14c6fe_173.png)

![](img/223aea760bce52b872e46ca99b14c6fe_175.png)

![](img/223aea760bce52b872e46ca99b14c6fe_177.png)

![](img/223aea760bce52b872e46ca99b14c6fe_178.png)

![](img/223aea760bce52b872e46ca99b14c6fe_179.png)

![](img/223aea760bce52b872e46ca99b14c6fe_180.png)

![](img/223aea760bce52b872e46ca99b14c6fe_182.png)

![](img/223aea760bce52b872e46ca99b14c6fe_184.png)

简单来说，感知器计算输入特征的加权和，然后根据这个和的正负来决定类别。

![](img/223aea760bce52b872e46ca99b14c6fe_186.png)

![](img/223aea760bce52b872e46ca99b14c6fe_187.png)

![](img/223aea760bce52b872e46ca99b14c6fe_189.png)

![](img/223aea760bce52b872e46ca99b14c6fe_191.png)

![](img/223aea760bce52b872e46ca99b14c6fe_193.png)

![](img/223aea760bce52b872e46ca99b14c6fe_195.png)

![](img/223aea760bce52b872e46ca99b14c6fe_196.png)

![](img/223aea760bce52b872e46ca99b14c6fe_198.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_200.png)

![](img/223aea760bce52b872e46ca99b14c6fe_202.png)

![](img/223aea760bce52b872e46ca99b14c6fe_203.png)

![](img/223aea760bce52b872e46ca99b14c6fe_205.png)

![](img/223aea760bce52b872e46ca99b14c6fe_206.png)

![](img/223aea760bce52b872e46ca99b14c6fe_207.png)

![](img/223aea760bce52b872e46ca99b14c6fe_209.png)

![](img/223aea760bce52b872e46ca99b14c6fe_210.png)

![](img/223aea760bce52b872e46ca99b14c6fe_211.png)

## 3. 感知器学习算法 🔄

![](img/223aea760bce52b872e46ca99b14c6fe_213.png)

![](img/223aea760bce52b872e46ca99b14c6fe_214.png)

![](img/223aea760bce52b872e46ca99b14c6fe_216.png)

![](img/223aea760bce52b872e46ca99b14c6fe_217.png)

![](img/223aea760bce52b872e46ca99b14c6fe_218.png)

![](img/223aea760bce52b872e46ca99b14c6fe_220.png)

![](img/223aea760bce52b872e46ca99b14c6fe_222.png)

![](img/223aea760bce52b872e46ca99b14c6fe_224.png)

感知器学习算法通过不断更新权重和偏置项来学习正确的线性决策边界。这是一个迭代的过程，目标是找到一组参数，使得所有训练样本都能被正确分类。

![](img/223aea760bce52b872e46ca99b14c6fe_225.png)

![](img/223aea760bce52b872e46ca99b14c6fe_227.png)

![](img/223aea760bce52b872e46ca99b14c6fe_229.png)

![](img/223aea760bce52b872e46ca99b14c6fe_231.png)

![](img/223aea760bce52b872e46ca99b14c6fe_232.png)

![](img/223aea760bce52b872e46ca99b14c6fe_233.png)

![](img/223aea760bce52b872e46ca99b14c6fe_234.png)

![](img/223aea760bce52b872e46ca99b14c6fe_236.png)

以下是感知器学习算法的步骤：

![](img/223aea760bce52b872e46ca99b14c6fe_238.png)

![](img/223aea760bce52b872e46ca99b14c6fe_240.png)

![](img/223aea760bce52b872e46ca99b14c6fe_242.png)

![](img/223aea760bce52b872e46ca99b14c6fe_243.png)

![](img/223aea760bce52b872e46ca99b14c6fe_245.png)

![](img/223aea760bce52b872e46ca99b14c6fe_247.png)

![](img/223aea760bce52b872e46ca99b14c6fe_249.png)

![](img/223aea760bce52b872e46ca99b14c6fe_251.png)

![](img/223aea760bce52b872e46ca99b14c6fe_252.png)

1.  **初始化**：将权重向量 `W` 和偏置项 `b` 初始化为0（或小的随机值）。
2.  **迭代训练**：对于训练集中的每个数据点 `(x_i, y_i)`：
    *   使用当前参数计算预测值：`y_pred = sign(W^T * x_i + b)`。
    *   **如果预测错误**（即 `y_pred != y_i`），则更新参数：
        *   **公式**：`W = W + y_i * x_i`
        *   **公式**：`b = b + y_i`
    *   如果预测正确，则参数保持不变。
3.  **重复**：遍历整个训练集多次（称为“轮数”），直到模型在训练集上不再犯错误或达到预设的迭代次数。

![](img/223aea760bce52b872e46ca99b14c6fe_253.png)

![](img/223aea760bce52b872e46ca99b14c6fe_254.png)

![](img/223aea760bce52b872e46ca99b14c6fe_256.png)

![](img/223aea760bce52b872e46ca99b14c6fe_258.png)

![](img/223aea760bce52b872e46ca99b14c6fe_260.png)

![](img/223aea760bce52b872e46ca99b14c6fe_262.png)

![](img/223aea760bce52b872e46ca99b14c6fe_264.png)

![](img/223aea760bce52b872e46ca99b14c6fe_265.png)

这个更新规则非常直观：当模型对一个正类样本（`y_i = +1`）预测为负时，我们就将权重向量向该样本的方向增加（`W + x_i`）；反之，对一个负类样本（`y_i = -1`）预测为正时，就将权重向量向该样本的反方向调整（`W - x_i`）。偏置项的更新同理。

![](img/223aea760bce52b872e46ca99b14c6fe_267.png)

![](img/223aea760bce52b872e46ca99b14c6fe_268.png)

![](img/223aea760bce52b872e46ca99b14c6fe_269.png)

![](img/223aea760bce52b872e46ca99b14c6fe_270.png)

![](img/223aea760bce52b872e46ca99b14c6fe_272.png)

![](img/223aea760bce52b872e46ca99b14c6fe_274.png)

![](img/223aea760bce52b872e46ca99b14c6fe_276.png)

![](img/223aea760bce52b872e46ca99b14c6fe_278.png)

![](img/223aea760bce52b872e46ca99b14c6fe_279.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_281.png)

![](img/223aea760bce52b872e46ca99b14c6fe_283.png)

![](img/223aea760bce52b872e46ca99b14c6fe_285.png)

![](img/223aea760bce52b872e46ca99b14c6fe_286.png)

![](img/223aea760bce52b872e46ca99b14c6fe_288.png)

![](img/223aea760bce52b872e46ca99b14c6fe_290.png)

![](img/223aea760bce52b872e46ca99b14c6fe_292.png)

![](img/223aea760bce52b872e46ca99b14c6fe_294.png)

![](img/223aea760bce52b872e46ca99b14c6fe_296.png)

## 4. 在线学习 🌊

![](img/223aea760bce52b872e46ca99b14c6fe_298.png)

![](img/223aea760bce52b872e46ca99b14c6fe_300.png)

![](img/223aea760bce52b872e46ca99b14c6fe_302.png)

![](img/223aea760bce52b872e46ca99b14c6fe_304.png)

![](img/223aea760bce52b872e46ca99b14c6fe_306.png)

![](img/223aea760bce52b872e46ca99b14c6fe_308.png)

上一节我们介绍了感知器如何通过迭代更新来学习。本节中，我们来看看一种非常适合感知器的学习范式——在线学习。

![](img/223aea760bce52b872e46ca99b14c6fe_309.png)

![](img/223aea760bce52b872e46ca99b14c6fe_311.png)

![](img/223aea760bce52b872e46ca99b14c6fe_313.png)

![](img/223aea760bce52b872e46ca99b14c6fe_314.png)

![](img/223aea760bce52b872e46ca99b14c6fe_316.png)

![](img/223aea760bce52b872e46ca99b14c6fe_318.png)

![](img/223aea760bce52b872e46ca99b14c6fe_319.png)

![](img/223aea760bce52b872e46ca99b14c6fe_321.png)

![](img/223aea760bce52b872e46ca99b14c6fe_323.png)

在线学习是一种机器学习范式，它允许模型在数据流中逐个或逐小批地接收数据并立即更新。与传统的批量学习（需要收集所有数据后再一次性训练）相比，在线学习具有以下特点：
*   **适应性强**：可以快速适应数据分布的变化。
*   **内存效率高**：无需存储全部历史数据，处理完即可丢弃。
*   **计算高效**：每次只基于少量新数据更新，适合实时或流式数据场景。

![](img/223aea760bce52b872e46ca99b14c6fe_325.png)

![](img/223aea760bce52b872e46ca99b14c6fe_326.png)

![](img/223aea760bce52b872e46ca99b14c6fe_328.png)

![](img/223aea760bce52b872e46ca99b14c6fe_330.png)

![](img/223aea760bce52b872e46ca99b14c6fe_332.png)

![](img/223aea760bce52b872e46ca99b14c6fe_333.png)

![](img/223aea760bce52b872e46ca99b14c6fe_335.png)

![](img/223aea760bce52b872e46ca99b14c6fe_337.png)

许多现实世界的应用，如垃圾邮件过滤、股票价格预测、推荐系统等，都受益于在线学习。

![](img/223aea760bce52b872e46ca99b14c6fe_339.png)

![](img/223aea760bce52b872e46ca99b14c6fe_340.png)

![](img/223aea760bce52b872e46ca99b14c6fe_341.png)

![](img/223aea760bce52b872e46ca99b14c6fe_343.png)

![](img/223aea760bce52b872e46ca99b14c6fe_345.png)

![](img/223aea760bce52b872e46ca99b14c6fe_346.png)

![](img/223aea760bce52b872e46ca99b14c6fe_348.png)

![](img/223aea760bce52b872e46ca99b14c6fe_349.png)

![](img/223aea760bce52b872e46ca99b14c6fe_350.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_352.png)

![](img/223aea760bce52b872e46ca99b14c6fe_354.png)

![](img/223aea760bce52b872e46ca99b14c6fe_356.png)

![](img/223aea760bce52b872e46ca99b14c6fe_358.png)

![](img/223aea760bce52b872e46ca99b14c6fe_359.png)

![](img/223aea760bce52b872e46ca99b14c6fe_361.png)

![](img/223aea760bce52b872e46ca99b14c6fe_363.png)

![](img/223aea760bce52b872e46ca99b14c6fe_365.png)

## 5. 感知器在线学习 ⚡

![](img/223aea760bce52b872e46ca99b14c6fe_367.png)

![](img/223aea760bce52b872e46ca99b14c6fe_369.png)

![](img/223aea760bce52b872e46ca99b14c6fe_371.png)

![](img/223aea760bce52b872e46ca99b14c6fe_373.png)

![](img/223aea760bce52b872e46ca99b14c6fe_374.png)

![](img/223aea760bce52b872e46ca99b14c6fe_376.png)

![](img/223aea760bce52b872e46ca99b14c6fe_378.png)

![](img/223aea760bce52b872e46ca99b14c6fe_380.png)

![](img/223aea760bce52b872e46ca99b14c6fe_381.png)

感知器天然适合在线学习场景。其算法步骤与之前介绍的基本相同，但强调了数据是顺序到达的：

![](img/223aea760bce52b872e46ca99b14c6fe_382.png)

![](img/223aea760bce52b872e46ca99b14c6fe_384.png)

![](img/223aea760bce52b872e46ca99b14c6fe_385.png)

![](img/223aea760bce52b872e46ca99b14c6fe_386.png)

![](img/223aea760bce52b872e46ca99b14c6fe_387.png)

![](img/223aea760bce52b872e46ca99b14c6fe_388.png)

![](img/223aea760bce52b872e46ca99b14c6fe_390.png)

![](img/223aea760bce52b872e46ca99b14c6fe_392.png)

1.  初始化权重 `W` 和偏置 `b`。
2.  对于**顺序到达**的每一个数据样本 `(x_t, y_t)`：
    *   做出预测：`y_pred = sign(W^T * x_t + b)`。
    *   如果预测错误，则立即更新：`W = W + y_t * x_t`， `b = b + y_t`。
    *   然后处理下一个样本。
3.  模型在整个数据流中持续学习和更新。

![](img/223aea760bce52b872e46ca99b14c6fe_394.png)

![](img/223aea760bce52b872e46ca99b14c6fe_395.png)

![](img/223aea760bce52b872e46ca99b14c6fe_396.png)

![](img/223aea760bce52b872e46ca99b14c6fe_397.png)

![](img/223aea760bce52b872e46ca99b14c6fe_399.png)

![](img/223aea760bce52b872e46ca99b14c6fe_401.png)

![](img/223aea760bce52b872e46ca99b14c6fe_402.png)

![](img/223aea760bce52b872e46ca99b14c6fe_403.png)

这种“来一个，学一个，更新一次”的模式，正是典型的在线学习。

![](img/223aea760bce52b872e46ca99b14c6fe_404.png)

![](img/223aea760bce52b872e46ca99b14c6fe_405.png)

![](img/223aea760bce52b872e46ca99b14c6fe_406.png)

![](img/223aea760bce52b872e46ca99b14c6fe_407.png)

![](img/223aea760bce52b872e46ca99b14c6fe_408.png)

![](img/223aea760bce52b872e46ca99b14c6fe_409.png)

![](img/223aea760bce52b872e46ca99b14c6fe_411.png)

![](img/223aea760bce52b872e46ca99b14c6fe_412.png)

![](img/223aea760bce52b872e46ca99b14c6fe_413.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_415.png)

![](img/223aea760bce52b872e46ca99b14c6fe_417.png)

![](img/223aea760bce52b872e46ca99b14c6fe_419.png)

![](img/223aea760bce52b872e46ca99b14c6fe_420.png)

![](img/223aea760bce52b872e46ca99b14c6fe_421.png)

![](img/223aea760bce52b872e46ca99b14c6fe_423.png)

![](img/223aea760bce52b872e46ca99b14c6fe_425.png)

![](img/223aea760bce52b872e46ca99b14c6fe_426.png)

## 6. 感知器的优势 ✅

![](img/223aea760bce52b872e46ca99b14c6fe_428.png)

![](img/223aea760bce52b872e46ca99b14c6fe_430.png)

![](img/223aea760bce52b872e46ca99b14c6fe_432.png)

![](img/223aea760bce52b872e46ca99b14c6fe_434.png)

![](img/223aea760bce52b872e46ca99b14c6fe_436.png)

![](img/223aea760bce52b872e46ca99b14c6fe_437.png)

![](img/223aea760bce52b872e46ca99b14c6fe_438.png)

![](img/223aea760bce52b872e46ca99b14c6fe_440.png)

![](img/223aea760bce52b872e46ca99b14c6fe_442.png)

感知器模型虽然简单，但具有一些显著优点：
*   **简单直观**：模型和算法都非常简单，易于实现和理解，是学习神经网络的基础。
*   **高效**：在线学习模式下，每次更新计算量小，收敛速度（对于线性可分数据）有理论保证。
*   **对某些噪声鲁棒**：更新只发生在错误分类的样本上，对部分异常值不敏感。

![](img/223aea760bce52b872e46ca99b14c6fe_443.png)

![](img/223aea760bce52b872e46ca99b14c6fe_445.png)

![](img/223aea760bce52b872e46ca99b14c6fe_446.png)

![](img/223aea760bce52b872e46ca99b14c6fe_447.png)

![](img/223aea760bce52b872e46ca99b14c6fe_449.png)

![](img/223aea760bce52b872e46ca99b14c6fe_450.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_452.png)

![](img/223aea760bce52b872e46ca99b14c6fe_454.png)

![](img/223aea760bce52b872e46ca99b14c6fe_455.png)

![](img/223aea760bce52b872e46ca99b14c6fe_457.png)

![](img/223aea760bce52b872e46ca99b14c6fe_459.png)

![](img/223aea760bce52b872e46ca99b14c6fe_461.png)

![](img/223aea760bce52b872e46ca99b14c6fe_462.png)

![](img/223aea760bce52b872e46ca99b14c6fe_464.png)

![](img/223aea760bce52b872e46ca99b14c6fe_466.png)

## 7. 感知器的局限性 ⚠️

![](img/223aea760bce52b872e46ca99b14c6fe_467.png)

![](img/223aea760bce52b872e46ca99b14c6fe_469.png)

![](img/223aea760bce52b872e46ca99b14c6fe_471.png)

![](img/223aea760bce52b872e46ca99b14c6fe_473.png)

![](img/223aea760bce52b872e46ca99b14c6fe_475.png)

![](img/223aea760bce52b872e46ca99b14c6fe_477.png)

![](img/223aea760bce52b872e46ca99b14c6fe_479.png)

然而，感知器也有其固有的局限性：
*   **线性假设**：感知器只能解决**线性可分**的问题。如果数据无法用一个超平面完美分开（例如异或问题），感知器将永远无法收敛到零错误。
*   **稳定性**：对于线性可分数据，最终的分离超平面不唯一，取决于训练样本的顺序和初始值。
*   **无法直接提供概率**：它只输出类别标签，而不像逻辑回归那样输出属于某一类的概率。

![](img/223aea760bce52b872e46ca99b14c6fe_480.png)

![](img/223aea760bce52b872e46ca99b14c6fe_482.png)

![](img/223aea760bce52b872e46ca99b14c6fe_484.png)

![](img/223aea760bce52b872e46ca99b14c6fe_485.png)

![](img/223aea760bce52b872e46ca99b14c6fe_486.png)

![](img/223aea760bce52b872e46ca99b14c6fe_487.png)

![](img/223aea760bce52b872e46ca99b14c6fe_489.png)

![](img/223aea760bce52b872e46ca99b14c6fe_491.png)

![](img/223aea760bce52b872e46ca99b14c6fe_493.png)

---

![](img/223aea760bce52b872e46ca99b14c6fe_495.png)

![](img/223aea760bce52b872e46ca99b14c6fe_497.png)

![](img/223aea760bce52b872e46ca99b14c6fe_499.png)

![](img/223aea760bce52b872e46ca99b14c6fe_500.png)

![](img/223aea760bce52b872e46ca99b14c6fe_501.png)

![](img/223aea760bce52b872e46ca99b14c6fe_502.png)

![](img/223aea760bce52b872e46ca99b14c6fe_504.png)

![](img/223aea760bce52b872e46ca99b14c6fe_506.png)

## 总结

![](img/223aea760bce52b872e46ca99b14c6fe_507.png)

![](img/223aea760bce52b872e46ca99b14c6fe_509.png)

![](img/223aea760bce52b872e46ca99b14c6fe_511.png)

![](img/223aea760bce52b872e46ca99b14c6fe_512.png)

![](img/223aea760bce52b872e46ca99b14c6fe_513.png)

![](img/223aea760bce52b872e46ca99b14c6fe_515.png)

![](img/223aea760bce52b872e46ca99b14c6fe_517.png)

本节课中，我们一起学习了机器学习中的经典模型——感知器。我们了解了它的数学模型 `y = sign(W^T * x + b)`，掌握了其通过错误驱动进行参数更新的学习算法。更重要的是，我们探讨了在线学习这一重要范式，并看到感知器如何自然地应用于其中，实现对新数据的快速适应。

![](img/223aea760bce52b872e46ca99b14c6fe_518.png)

![](img/223aea760bce52b872e46ca99b14c6fe_519.png)

![](img/223aea760bce52b872e46ca99b14c6fe_521.png)

![](img/223aea760bce52b872e46ca99b14c6fe_523.png)

![](img/223aea760bce52b872e46ca99b14c6fe_524.png)

![](img/223aea760bce52b872e46ca99b14c6fe_525.png)

![](img/223aea760bce52b872e46ca99b14c6fe_526.png)

感知器是神经网络和支持向量机等更复杂模型的基石。理解它的原理、优势和局限，对我们后续深入学习至关重要。