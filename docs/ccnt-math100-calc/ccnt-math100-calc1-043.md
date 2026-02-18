# 第一部分 43：优化问题示例 - 给定固定体积，求最小表面积 📦

在本节课中，我们将一起研究一个具体的优化问题。我们将探讨一个底面为正方形的盒子，在体积固定为100立方单位的前提下，如何找到使其表面积最小的盒子高度。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_1.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_2.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_3.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_4.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_5.png)

---

![](img/f42fe1ab28fb33eeeed3467d912d33a2_7.png)

## 🎨 第一步：绘制并标注示意图

![](img/f42fe1ab28fb33eeeed3467d912d33a2_8.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_10.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_11.png)

解决优化问题的第一步，通常是绘制一个能清晰反映问题情况的示意图。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_12.png)

上一节我们介绍了问题背景，本节中我们来看看如何将问题可视化。

以下是我们绘制的示意图，它代表了一个底面为正方形的盒子：

![](img/f42fe1ab28fb33eeeed3467d912d33a2_14.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_15.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_16.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_1.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_2.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_3.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_4.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_5.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_17.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_18.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_19.png)

仅仅画图还不够，我们需要对图形进行标注，并且要严格使用定义好的符号，避免在推导过程中使用含义不清的变量。

*   底面是正方形，其边长我们标记为 **`x`**。
*   盒子的高度我们标记为 **`y`**。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_21.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_22.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_23.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_14.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_15.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_16.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_17.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_18.png)
![](img/f42fe1ab33eeeed3467d912d33a2_19.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_24.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_25.png)

---

## 📐 第二步：建立约束方程与目标方程

![](img/f42fe1ab28fb33eeeed3467d912d33a2_27.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_28.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_29.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_30.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_31.png)

在明确了变量之后，接下来我们需要用数学公式来描述问题中的约束条件和我们要优化的目标。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_33.png)

### 约束方程（体积）

![](img/f42fe1ab28fb33eeeed3467d912d33a2_34.png)

已知盒子的体积固定为100。根据长方体体积公式（长 × 宽 × 高），我们可以写出：

![](img/f42fe1ab28fb33eeeed3467d912d33a2_36.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_37.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_38.png)

**`V = x * x * y = x²y = 100`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_40.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_41.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_21.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_22.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_23.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_24.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_25.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_43.png)

由于问题最终要求的是高度 `y`，我们选择从这个方程中解出 `x`，以便在后续步骤中消去 `x`，将问题转化为只关于 `y` 的函数。

由 `x²y = 100` 可得：
**`x² = 100 / y`**
进而：
**`x = 10 / √y`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_27.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_28.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_29.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_30.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_31.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_45.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_46.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_47.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_48.png)

### 目标方程（表面积）

![](img/f42fe1ab28fb33eeeed3467d912d33a2_49.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_50.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_51.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_52.png)

我们的目标是**最小化盒子的表面积**。一个长方体有6个面：
*   底面和顶面：面积均为 `x²`，合计为 `2x²`。
*   四个侧面：由于底面是正方形，四个侧面完全相同，每个面积为 `x * y`，合计为 `4xy`。

因此，表面积 `S` 的公式为：
**`S = 2x² + 4xy`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_54.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_45.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_46.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_47.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_48.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_49.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_50.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_51.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_52.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_55.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_56.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_57.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_58.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_59.png)

---

![](img/f42fe1ab28fb33eeeed3467d912d33a2_61.png)

## 🔄 第三步：将目标方程转化为单变量函数

![](img/f42fe1ab28fb33eeeed3467d912d33a2_62.png)

现在，我们将约束方程中得到的 `x` 和 `x²` 的表达式代入表面积公式，从而得到一个只关于高度 `y` 的函数 `S(y)`。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_64.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_65.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_66.png)

代入 `x² = 100/y` 和 `x = 10/√y`：
**`S(y) = 2*(100/y) + 4*(10/√y)*y = 200/y + 40√y`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_68.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_69.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_61.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_62.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_64.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_65.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_66.png)

在继续之前，我们需要考虑函数的定义域。高度 `y` 必须为正数 (`y > 0`)，因为零高度或负高度没有物理意义。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_71.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_72.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_73.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_74.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_75.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_71.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_72.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_73.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_74.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_75.png)

---

![](img/f42fe1ab28fb33eeeed3467d912d33a2_77.png)

## 📉 第四步：求导并寻找临界点

![](img/f42fe1ab28fb33eeeed3467d912d33a2_78.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_80.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_81.png)

为了找到使表面积 `S(y)` 最小的 `y` 值，我们需要计算其导数 `S'(y)`，并令其等于零来求解临界点。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_83.png)

对 `S(y) = 200/y + 40√y` 求导：
**`S'(y) = -200/y² + 40*(1/(2√y)) = -200/y² + 20/√y`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_84.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_85.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_87.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_80.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_81.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_83.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_84.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_85.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_88.png)

令导数等于零以寻找临界点：
**`-200/y² + 20/√y = 0`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_90.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_91.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_87.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_88.png)

为了求解这个方程，两边同时乘以 `y²` 进行化简：
**`-200 + 20*y^(3/2) = 0`**
**`20*y^(3/2) = 200`**
**`y^(3/2) = 10`**
**`y = 10^(2/3) = ³√100`**

![](img/f42fe1ab28fb33eeeed3467d912d33a2_93.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_94.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_95.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_90.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_91.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_93.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_94.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_95.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_96.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_97.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_96.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_97.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_99.png)

我们得到了一个临界点：**`y = ³√100`**。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_101.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_99.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_101.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_103.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_104.png)

---

![](img/f42fe1ab28fb33eeeed3467d912d33a2_105.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_107.png)

## ✅ 第五步：使用一阶导数检验法验证最小值

![](img/f42fe1ab28fb33eeeed3467d912d33a2_108.png)

找到临界点后，我们需要确定它对应的是最小值还是最大值。我们将使用**一阶导数检验法**来进行验证。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_110.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_111.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_112.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_103.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_104.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_105.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_107.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_108.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_113.png)

我们在临界点 `y = ³√100` 左右两侧各选一个测试点，代入导数 `S'(y)` 观察符号变化。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_115.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_116.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_117.png)

*   当 `y < ³√100` 时（例如取一个更小的正数），`-200/y²` 项负得更多，`20/√y` 项正得更少，因此 `S'(y) < 0`，函数 `S(y)` **递减**。
*   当 `y > ³√100` 时（例如取一个更大的正数），`-200/y²` 项负得更少（绝对值变小），`20/√y` 项正得更多，因此 `S'(y) > 0`，函数 `S(y)` **递增**。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_110.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_111.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_112.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_113.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_115.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_116.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_117.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_119.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_120.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_121.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_119.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_120.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_121.png)

导数符号由负变正，意味着函数先减后增。因此，在 `y = ³√100` 处，函数 `S(y)` 取得**极小值**，也就是我们寻找的最小表面积对应的高度。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_123.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_123.png)

---

## 🎯 结论与总结

![](img/f42fe1ab28fb33eeeed3467d912d33a2_125.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_126.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_127.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_128.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_129.png)

回顾原问题：求一个体积为100的底面为正方形的盒子的高度，使得其表面积最小。我们通过上述步骤成功地解决了这个问题。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_130.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_131.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_125.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_126.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_127.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_128.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_129.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_130.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_131.png)

本节课中，我们一起学习并实践了解决优化问题的标准流程：

![](img/f42fe1ab28fb33eeeed3467d912d33a2_133.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_134.png)

1.  **绘制示意图并标注变量**：将文字描述转化为直观的图形和明确的符号。
2.  **建立数学模型**：根据问题写出**约束方程**（本例中的体积公式）和**目标方程**（本例中的表面积公式）。
3.  **转化为单变量函数**：利用约束方程，将目标方程化简为只含一个自变量（通常是要求解的量）的函数。
4.  **求导寻找临界点**：对目标函数求导，令导数为零，解出所有临界点。
5.  **检验并得出结论**：使用一阶导数检验法（或二阶导数检验法）判断临界点是极大值点还是极小值点，从而得到问题的最优解。

![](img/f42fe1ab28fb33eeeed3467d912d33a2_135.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_136.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_137.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_138.png)

![](img/f42fe1ab28fb33eeeed3467d912d33a2_133.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_134.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_135.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_136.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_137.png)
![](img/f42fe1ab28fb33eeeed3467d912d33a2_138.png)