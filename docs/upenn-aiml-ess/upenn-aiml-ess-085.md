# 21：线性回归讲解-第一部分 📊

![](img/6c0f877a8d14bf6edd1c73326237d57a_0.png)

在本节课中，我们将要学习线性回归的基础知识。我们将使用两个数据集（大学数据和波士顿数据），通过Python实践线性回归模型的构建、评估和解读。课程将涵盖从数据导入、模型拟合到结果分析的完整流程。

![](img/6c0f877a8d14bf6edd1c73326237d57a_2.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_3.png)

---

![](img/6c0f877a8d14bf6edd1c73326237d57a_4.png)

## 数据准备与导入 📥

首先，我们需要导入必要的Python库并加载数据集。

![](img/6c0f877a8d14bf6edd1c73326237d57a_6.png)

以下是本教程所需的库：
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import statsmodels.api as sm
import statsmodels.formula.api as smf
from sklearn.linear_model import LinearRegression
```

![](img/6c0f877a8d14bf6edd1c73326237d57a_8.png)

现在，我们将大学数据集作为Pandas数据框导入，并重命名列以便于处理。
```python
data = pd.read_csv('college.csv')
data.columns = ['new_name1', 'new_name2', ...]  # 根据实际列名重命名
data.head()
```

在数据集中，每一行代表一所大学，每一列代表一个特征。在Python中，第一个索引是0。

![](img/6c0f877a8d14bf6edd1c73326237d57a_10.png)

---

## 数据预处理 🔧

![](img/6c0f877a8d14bf6edd1c73326237d57a_12.png)

上一节我们导入了原始数据，本节中我们将对数据进行预处理，添加一个新列。

![](img/6c0f877a8d14bf6edd1c73326237d57a_14.png)

我们将添加一个名为“接受率”的新列，它是“录取人数”与“申请人数”的比值。
```python
data['accept_rate'] = data['accept'] / data['apps']
```

---

## 使用Statsmodels进行线性回归 📈

![](img/6c0f877a8d14bf6edd1c73326237d57a_16.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_18.png)

现在，我们开始使用普通最小二乘法构建线性回归模型。首先介绍使用`statsmodels`库的两种方法。

以下是使用`smf.ols`方法进行拟合的步骤：
```python
model_smf = smf.ols('grad_rate ~ top25perc', data=data)
fit0 = model_smf.fit()
print(fit0.summary())
```

在结果摘要中，我们需要关注几个关键统计量：
*   **R-squared值**：衡量模型拟合优度，本例中为0.2028。
*   **系数估计值**：
    *   截距 `β0_hat` = 42
    *   斜率 `β1_hat` = 0.41
*   **标准误差、t值、P值和95%置信区间**：例如，斜率`β1`的95%置信区间为[0.36, 0.46]。

![](img/6c0f877a8d14bf6edd1c73326237d57a_20.png)

---

## 使用Statsmodels API的另一种方法

除了公式接口，`statsmodels`还提供了直接的API接口进行线性回归。

![](img/6c0f877a8d14bf6edd1c73326237d57a_22.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_23.png)

以下是使用`sm.OLS`方法的步骤。注意，使用此方法时需要手动为自变量添加常数项以包含截距。
```python
X = sm.add_constant(data['top25perc'])  # 添加常数项
y = data['grad_rate']
model_sm = sm.OLS(y, X)
fit1 = model_sm.fit()
print(fit1.summary())
```

![](img/6c0f877a8d14bf6edd1c73326237d57a_25.png)

此方法得到的结果与第一种方法完全相同。

![](img/6c0f877a8d14bf6edd1c73326237d57a_27.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_29.png)

---

## 使用Scikit-learn进行线性回归 🤖

除了`statsmodels`，我们还可以使用`scikit-learn`库来构建线性回归模型。

![](img/6c0f877a8d14bf6edd1c73326237d57a_31.png)

以下是使用`scikit-learn`的步骤：
```python
X_sk = data[['top25perc']]  # 注意双括号，以保持DataFrame结构
y_sk = data['grad_rate']
model_sk = LinearRegression(fit_intercept=True)
fit2 = model_sk.fit(X_sk, y_sk)

# 获取系数
print(f"截距 (β0_hat): {fit2.intercept_}")
print(f"斜率 (β1_hat): {fit2.coef_[0]}")
```

![](img/6c0f877a8d14bf6edd1c73326237d57a_33.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_34.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_36.png)

所有方法得到的系数估计值都是一致的。斜率`β1_hat = 0.41`的含义是：自变量`top25perc`每增加1%，因变量`grad_rate`平均增加0.41%。

---

## 模型可视化与诊断 👁️

上一节我们拟合了模型，本节中我们通过绘图来直观展示拟合效果并进行诊断。

首先，我们绘制原始数据散点图和拟合的回归线。
```python
plt.scatter(data['top25perc'], data['grad_rate'], color='red', label='原始数据')
plt.plot(data['top25perc'], fit0.fittedvalues, color='blue', label='拟合直线')
plt.xlabel('top25perc')
plt.ylabel('grad_rate')
plt.legend()
plt.show()
```

![](img/6c0f877a8d14bf6edd1c73326237d57a_38.png)

其次，我们可以使用Q-Q图来检查残差是否服从正态分布，这是线性回归的重要假设之一。
```python
import statsmodels.api as sm
sm.qqplot(fit0.resid, line='s')
plt.show()
```

![](img/6c0f877a8d14bf6edd1c73326237d57a_40.png)

此外，绘制残差图可以检查模型是否存在异方差等问题。
```python
plt.scatter(fit0.fittedvalues, fit0.resid)
plt.axhline(y=0, color='red', linestyle='--')
plt.xlabel('拟合值')
plt.ylabel('残差')
plt.show()
```

---

![](img/6c0f877a8d14bf6edd1c73326237d57a_42.png)

## 关键统计量计算 🧮

基于模型结果，我们可以计算几个关键的统计量来评估模型性能。

以下是这些统计量的定义和计算公式：
*   **残差平方和**：`RSS = Σ(y_i - ŷ_i)²`
*   **残差标准误**：`RSE = sqrt(RSS / (n - p - 1))`，其中`n`是样本数，`p`是自变量个数（本例中p=1）。
*   **总平方和**：`TSS = Σ(y_i - ȳ)²`
*   **R-squared**：`R² = (TSS - RSS) / TSS`

我们可以手动编程计算这些值：
```python
RSS = np.sum((y - fit0.fittedvalues) ** 2)
n = len(y)
RSE = np.sqrt(RSS / (n - 2))  # p=1, 所以自由度是 n-2
TSS = np.sum((y - np.mean(y)) ** 2)
R_squared_manual = (TSS - RSS) / TSS
```

当然，我们也可以直接从拟合结果中获取R-squared值：`fit0.rsquared`。RSE是测量误差标准差`σ`的估计值，对于计算置信区间至关重要。

---

## 假设检验与P值 🧪

在统计学中，我们通过假设检验来判断自变量是否对因变量有显著影响。

我们建立以下假设：
*   **零假设 H₀**：自变量与因变量无关，即 `β1 = 0`。
*   **备择假设 H₁**：自变量与因变量有关，即 `β1 ≠ 0`。

我们使用P值来做出统计决策。通常将显著性水平设为0.05。
*   如果 **P值 < 0.05**，则在95%的置信水平下**拒绝零假设**，认为自变量显著。
*   如果 **P值 ≥ 0.05**，则**无法拒绝零假设**，认为自变量不显著。

在本例的摘要表中，`top25perc`对应的P值远小于0.05，因此我们拒绝零假设，得出结论：`top25perc`与`grad_rate`之间存在显著的统计关系。

---

## 预测与置信区间 🔮

线性回归模型不仅可以给出点预测，还可以给出预测值的置信区间，以量化预测的不确定性。

对于一个给定的自变量值`x_new`，其点预测为：
`ŷ_new = β0_hat + β1_hat * x_new`

例如，当`top25perc = 50`时：
```python
x_new = 50
y_pred = fit0.params['Intercept'] + fit0.params['top25perc'] * x_new
```

该点的预测值约为60%。我们还可以构建该预测值的95%置信区间：
`预测区间 = ŷ_new ± 2 * RSE`

![](img/6c0f877a8d14bf6edd1c73326237d57a_44.png)

我们可以编程计算：
```python
y_pred_lower = y_pred - 2 * RSE
y_pred_upper = y_pred + 2 * RSE
print(f"95% 预测区间: [{y_pred_lower:.2f}, {y_pred_upper:.2f}]")
```

![](img/6c0f877a8d14bf6edd1c73326237d57a_46.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_48.png)

对于`top25perc=50`，其毕业率的95%预测区间大约在36%到97%之间。这个区间较宽，表明对于单个观测值的预测存在相当大的不确定性。

![](img/6c0f877a8d14bf6edd1c73326237d57a_50.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_52.png)

---

![](img/6c0f877a8d14bf6edd1c73326237d57a_54.png)

## 总结 📝

![](img/6c0f877a8d14bf6edd1c73326237d57a_56.png)

本节课中我们一起学习了线性回归的第一部分。我们掌握了：
1.  使用`statsmodels`和`scikit-learn`库在Python中实现简单线性回归。
2.  解读回归摘要，理解系数、R-squared、P值等关键统计量的含义。
3.  通过可视化（散点图、拟合线、Q-Q图、残差图）来诊断模型。
4.  计算并理解RSS、RSE、TSS等核心统计量。
5.  进行假设检验，利用P值判断变量的统计显著性。
6.  使用拟合模型进行点预测，并构建预测值的置信区间。

![](img/6c0f877a8d14bf6edd1c73326237d57a_58.png)

这些内容是理解和使用线性回归模型的基础。在接下来的课程中，我们将在此基础上探讨更复杂的多元线性回归模型。