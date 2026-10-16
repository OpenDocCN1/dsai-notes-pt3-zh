

## Boosting 插图

- 弱分类器 1
- 权重增加
- 弱分类器 2
- 权重增加
- 弱分类器 3
- 最终分类器是弱分类器的组合

## AdaBoost 及其应用

AdaBoost 如何以及为什么有效？AdaBoost 想要达到什么目标？

### AdaBoost 算法

给定 \(\{(x_i,y_i)\}_{i=1}^m\)，其中 \(x_i \in X\)，\(y_i \in \{-1,+1\}\)。

- 初始化：\(D_1(i)=1/m\)，\(i=1,\ldots,m\)。
- 对于 \(t=1,\ldots,T\)：
  - 寻找分类器 \(h_t: X \to \{-1,+1\}\) 使其相对于 \(D_t\) 的误差最小：
    \[
    h_t = \arg\min_h \sum_i D_t(i)[y_i \neq h(x_i)], \qquad \epsilon_t = \sum_i D_t(i)[y_i \neq h_t(x_i)].
    \]
  - 赋予分类器权重：\(\alpha_t = \frac{1}{2}\ln\frac{1-\epsilon_t}{\epsilon_t}\)。
  - 更新分布：
    \[
    D_{t+1}(i) = \frac{D_t(i)\exp(-\alpha_t y_i h_t(x_i))}{Z_t},
    \]
    其中 \(Z_t\) 用于归一化。
- 输出最终分类器：
  \[
  \operatorname{sign}(H(x)) = \operatorname{sign}\left(\sum_t \alpha_t h_t(x)\right).
  \]

![](img/806dfb586cd1a39120c0a828715591b9_48_0.png)

### 目标

最终分类器：
\[
\operatorname{sign}(H(x)) = \operatorname{sign}\left(\sum_t \alpha_t h_t(x)\right).
\]

AdaBoost 最小化指数损失：
\[
\operatorname{loss}_{\exp}[H(x)] = \mathbb{E}_{x,y}[e^{-yH(x)}].
\]

等价地，它最大化间隔 \(yH(x)\)。

### 选择 \(\alpha_t\)

定义
\[
H_t(x) = H_{t-1}(x) + \alpha_t h_t(x), \qquad H_0(x)=0.
\]
则 \(H(x)=H_T(x)\)。

\[
\mathbb{E}_{x,y}[e^{-yH_T(x)}] = \mathbb{E}_x\left[\mathbb{E}_y[e^{-yH_{t-1}(x)-y\alpha_t h_t(x)} \mid x]\right].
\]

设
\[
\frac{\partial}{\partial\alpha_t}\mathbb{E}_{x,y}[e^{-yH_t(x)}]=0,
\]
故
\[
\mathbb{E}_x\left[e^{-H_{t-1}(x)}\left(-e^{-\alpha_t}P(y=h_t(x)) + e^{\alpha_t}P(y\neq h_t(x))\right)\right] = 0.
\]

因此
\[
\alpha_t = \frac{1}{2}\ln\frac{P(y=h_t(x))}{P(y\neq h_t(x))}
= \frac{1}{2}\ln\frac{1-\epsilon_t}{\epsilon_t},
\]
其中
\[
\epsilon_t = P(\text{error}) = \sum_i D_t(i)[y_i \neq h_t(x_i)].
\]

### 更新分布

分布更新与 \(D_{t+1}(i)=D_t(i)e^{-\alpha_t y_i h_t(x_i)}\) 成正比，归一化后：
\[
D_{t+1}(i) = \frac{D_t(i)e^{-\alpha_t y_i h_t(x_i)}}{Z_t},
\]
其中 \(Z_t\) 是归一化因子。

## AdaBoost 用于人脸检测

### 挑战

- 在图像上滑动窗口并在每个位置评估人脸模型。
- 滑动窗口检测器必须评估数万个位置/尺度组合。
- 人脸很少：每张图像 0–10 个。
  - 为了计算效率，我们应尽可能少地花费时间在非人脸窗口上。
  - 一张兆像素图像有 ~10^6 个像素和相当数量的候选人脸位置。
  - 为了避免每张图像都出现假阳性，我们的假阳性率必须小于 \(10^{-6}\)。

### Viola/Jones 人脸检测器

- 实时目标检测的开创性方法。
- 训练缓慢，但检测非常快。
- 关键思想：
  - 积分图像用于快速特征评估。
  - Boosting 用于特征选择。
  - 注意力级联用于快速拒绝非人脸窗口。

