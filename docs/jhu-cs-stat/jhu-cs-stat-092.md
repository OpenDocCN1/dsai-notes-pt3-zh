#  092：R语言教程 🧮

![](img/bb670bc78b38a2fb439576d2910375f8_1.png)

在本教程中，我们将学习如何在R语言中使用`gRain`包来构建和操作概率图模型。我们将通过一个具体的例子，演示如何定义变量、建立条件概率表、构建贝叶斯网络，并进行概率查询和推断。

![](img/bb670bc78b38a2fb439576d2910375f8_3.png)

![](img/bb670bc78b38a2fb439576d2910375f8_4.png)

![](img/bb670bc78b38a2fb439576d2910375f8_6.png)

## 概述

![](img/bb670bc78b38a2fb439576d2910375f8_8.png)

![](img/bb670bc78b38a2fb439576d2910375f8_9.png)

![](img/bb670bc78b38a2fb439576d2910375f8_11.png)

![](img/bb670bc78b38a2fb439576d2910375f8_13.png)

我们将创建一个关于天气、温度、外套和雨伞的简单贝叶斯网络。通过这个例子，你将学会如何将理论知识转化为可执行的R代码，并利用图模型进行概率计算。

![](img/bb670bc78b38a2fb439576d2910375f8_15.png)

![](img/bb670bc78b38a2fb439576d2910375f8_17.png)

---

![](img/bb670bc78b38a2fb439576d2910375f8_19.png)

![](img/bb670bc78b38a2fb439576d2910375f8_21.png)

## 环境准备与数据加载

![](img/bb670bc78b38a2fb439576d2910375f8_23.png)

![](img/bb670bc78b38a2fb439576d2910375f8_25.png)

![](img/bb670bc78b38a2fb439576d2910375f8_27.png)

首先，我们需要准备R环境并加载必要的库和工具。

![](img/bb670bc78b38a2fb439576d2910375f8_29.png)

![](img/bb670bc78b38a2fb439576d2910375f8_30.png)

![](img/bb670bc78b38a2fb439576d2910375f8_32.png)

![](img/bb670bc78b38a2fb439576d2910375f8_33.png)

![](img/bb670bc78b38a2fb439576d2910375f8_35.png)

```r
# 清除全局变量和图形
rm(list=ls())
graphics.off()

![](img/bb670bc78b38a2fb439576d2910375f8_37.png)

![](img/bb670bc78b38a2fb439576d2910375f8_39.png)

![](img/bb670bc78b38a2fb439576d2910375f8_41.png)

![](img/bb670bc78b38a2fb439576d2910375f8_43.png)

# 加载自定义工具库（需确保已安装gRain库）
source("stat_tools.R")
```

![](img/bb670bc78b38a2fb439576d2910375f8_45.png)

![](img/bb670bc78b38a2fb439576d2910375f8_47.png)

![](img/bb670bc78b38a2fb439576d2910375f8_49.png)

![](img/bb670bc78b38a2fb439576d2910375f8_51.png)

上一节我们完成了环境设置，本节中我们来看看如何定义网络中的变量及其概率分布。

![](img/bb670bc78b38a2fb439576d2910375f8_53.png)

![](img/bb670bc78b38a2fb439576d2910375f8_54.png)

![](img/bb670bc78b38a2fb439576d2910375f8_55.png)

![](img/bb670bc78b38a2fb439576d2910375f8_56.png)

## 定义变量与条件概率表

![](img/bb670bc78b38a2fb439576d2910375f8_57.png)

![](img/bb670bc78b38a2fb439576d2910375f8_59.png)

![](img/bb670bc78b38a2fb439576d2910375f8_60.png)

![](img/bb670bc78b38a2fb439576d2910375f8_62.png)

在计算机上构建概率图模型时，需要为每个变量上传其概率分布。我们通过条件概率表来实现这一点。`gRain`包中的`CPT`函数用于创建条件概率表实例。

![](img/bb670bc78b38a2fb439576d2910375f8_64.png)

![](img/bb670bc78b38a2fb439576d2910375f8_66.png)

![](img/bb670bc78b38a2fb439576d2910375f8_67.png)

以下是定义“温度”变量的示例：

![](img/bb670bc78b38a2fb439576d2910375f8_68.png)

![](img/bb670bc78b38a2fb439576d2910375f8_70.png)

![](img/bb670bc78b38a2fb439576d2910375f8_72.png)

![](img/bb670bc78b38a2fb439576d2910375f8_73.png)

![](img/bb670bc78b38a2fb439576d2910375f8_74.png)

```r
# 定义温度变量及其概率分布
temperature <- CPT(values = c(0.1, 0.4, 0.4, 0.1),
                   levels = c("<40", "40-59", "60-80", ">80"))
```
这段代码表示：温度低于40度的概率为10%，在40-59度之间的概率为40%，在60-80度之间的概率为40%，高于80度的概率为10%。

![](img/bb670bc78b38a2fb439576d2910375f8_76.png)

![](img/bb670bc78b38a2fb439576d2910375f8_78.png)

![](img/bb670bc78b38a2fb439576d2910375f8_79.png)

![](img/bb670bc78b38a2fb439576d2910375f8_81.png)

接下来，我们按照相同的方式定义其他变量。这个例子与之前视频讲座中的例子完全相同。

![](img/bb670bc78b38a2fb439576d2910375f8_83.png)

![](img/bb670bc78b38a2fb439576d2910375f8_84.png)

![](img/bb670bc78b38a2fb439576d2910375f8_86.png)

```r
# 定义天气变量
weather <- CPT(values = c(0.1, 0.5, 0.4),
               levels = c("rainy", "cloudy", "sunny"))

![](img/bb670bc78b38a2fb439576d2910375f8_88.png)

![](img/bb670bc78b38a2fb439576d2910375f8_90.png)

![](img/bb670bc78b38a2fb439576d2910375f8_91.png)

# 定义雨伞变量（条件于天气）
umbrella <- CPT(values = c(0.8, 0.2,  # 下雨时，雨伞打开的概率为80%，关闭为20%
                           0.1, 0.9,  # 多云时
                           0.01, 0.99), # 晴天时
                levels = c("open", "closed"),
                given = "weather")

![](img/bb670bc78b38a2fb439576d2910375f8_93.png)

![](img/bb670bc78b38a2fb439576d2910375f8_94.png)

![](img/bb670bc78b38a2fb439576d2910375f8_96.png)

![](img/bb670bc78b38a2fb439576d2910375f8_98.png)

# 定义外套变量（条件于天气和温度）
# 外套类型：无、雨衣、薄外套、厚外套
jacket <- CPT(values = c(0.01, 0.8, 0.15, 0.04,  # 温度<40，下雨
                          0.05, 0.7, 0.2, 0.05,   # 温度<40，多云
                          ... # 此处应填入完整的概率值矩阵
                         ),
              levels = c("none", "raincoat", "light", "heavy"),
              given = c("weather", "temperature"))
```
**注意**：在实际代码中，`jacket`的`values`参数需要一个很长的向量，其顺序必须与`levels`和`given`参数定义的组合顺序完全匹配，且所有概率之和必须为1。

![](img/bb670bc78b38a2fb439576d2910375f8_100.png)

![](img/bb670bc78b38a2fb439576d2910375f8_101.png)

![](img/bb670bc78b38a2fb439576d2910375f8_103.png)

![](img/bb670bc78b38a2fb439576d2910375f8_105.png)

现在，我们将所有变量放入一个列表中。

![](img/bb670bc78b38a2fb439576d2910375f8_107.png)

![](img/bb670bc78b38a2fb439576d2910375f8_109.png)

![](img/bb670bc78b38a2fb439576d2910375f8_111.png)

![](img/bb670bc78b38a2fb439576d2910375f8_113.png)

```r
# 将所有变量存入列表
var_list <- list(temperature = temperature,
                 weather = weather,
                 umbrella = umbrella,
                 jacket = jacket)
```

![](img/bb670bc78b38a2fb439576d2910375f8_115.png)

![](img/bb670bc78b38a2fb439576d2910375f8_116.png)

![](img/bb670bc78b38a2fb439576d2910375f8_118.png)

![](img/bb670bc78b38a2fb439576d2910375f8_120.png)

![](img/bb670bc78b38a2fb439576d2910375f8_122.png)

## 编译概率网络

![](img/bb670bc78b38a2fb439576d2910375f8_124.png)

![](img/bb670bc78b38a2fb439576d2910375f8_126.png)

![](img/bb670bc78b38a2fb439576d2910375f8_128.png)

定义了所有变量后，我们需要将它们编译成一个概率网络模型。

![](img/bb670bc78b38a2fb439576d2910375f8_130.png)

![](img/bb670bc78b38a2fb439576d2910375f8_131.png)

![](img/bb670bc78b38a2fb439576d2910375f8_133.png)

![](img/bb670bc78b38a2fb439576d2910375f8_134.png)

```r
# 编译条件概率表列表
prob_list <- compileCPT(var_list)

![](img/bb670bc78b38a2fb439576d2910375f8_136.png)

![](img/bb670bc78b38a2fb439576d2910375f8_138.png)

![](img/bb670bc78b38a2fb439576d2910375f8_140.png)

# 打印编译后的网络结构，以验证R语言是否正确理解了我们的系统
print(prob_list)
```
运行`print(prob_list)`后，输出会显示R识别出的变量及其依赖关系：概率`P(温度)`、`P(天气)`、`P(雨伞|天气)`和`P(外套|天气， 温度)`。

![](img/bb670bc78b38a2fb439576d2910375f8_142.png)

![](img/bb670bc78b38a2fb439576d2910375f8_144.png)

我们可以使用`summary`函数来查看每个变量的详细概率分布，确保其与我们的设定一致。

![](img/bb670bc78b38a2fb439576d2910375f8_146.png)

![](img/bb670bc78b38a2fb439576d2910375f8_148.png)

![](img/bb670bc78b38a2fb439576d2910375f8_150.png)

![](img/bb670bc78b38a2fb439576d2910375f8_152.png)

```r
# 查看概率列表的摘要信息
summary(prob_list)
```
摘要信息会显示每个状态的具体概率值，例如天气为雨天的概率是1%，多云5%，晴天4%等。对于条件概率表如`雨伞`，它会显示在每种天气条件下雨伞打开或关闭的概率。

![](img/bb670bc78b38a2fb439576d2910375f8_154.png)

![](img/bb670bc78b38a2fb439576d2910375f8_156.png)

![](img/bb670bc78b38a2fb439576d2910375f8_157.png)

![](img/bb670bc78b38a2fb439576d2910375f8_158.png)

## 构建与可视化贝叶斯网络

![](img/bb670bc78b38a2fb439576d2910375f8_160.png)

![](img/bb670bc78b38a2fb439576d2910375f8_161.png)

![](img/bb670bc78b38a2fb439576d2910375f8_163.png)

现在我们已经正确地将数据输入系统，让我们来构建并可视化一个贝叶斯网络。

![](img/bb670bc78b38a2fb439576d2910375f8_164.png)

![](img/bb670bc78b38a2fb439576d2910375f8_166.png)

![](img/bb670bc78b38a2fb439576d2910375f8_168.png)

```r
# 从概率列表创建图模型（贝叶斯网络）
graphical_model <- grain(prob_list)

![](img/bb670bc78b38a2fb439576d2910375f8_169.png)

![](img/bb670bc78b38a2fb439576d2910375f8_170.png)

![](img/bb670bc78b38a2fb439576d2910375f8_172.png)

![](img/bb670bc78b38a2fb439576d2910375f8_174.png)

![](img/bb670bc78b38a2fb439576d2910375f8_176.png)

# 为图形模型命名
GN1 <- graphical_model

![](img/bb670bc78b38a2fb439576d2910375f8_178.png)

![](img/bb670bc78b38a2fb439576d2910375f8_180.png)

![](img/bb670bc78b38a2fb439576d2910375f8_181.png)

# 绘制网络图
plot(GN1)
```
如果一切正确，绘图将展示我们系统的图形化表示。我们将看到`温度`和`天气`变量是`外套`变量的父节点，而`天气`是`雨伞`的唯一父节点。这个贝叶斯网络是一个有向无环图，反映了我之前定义的概率分布。

![](img/bb670bc78b38a2fb439576d2910375f8_182.png)

![](img/bb670bc78b38a2fb439576d2910375f8_184.png)

![](img/bb670bc78b38a2fb439576d2910375f8_186.png)

![](img/bb670bc78b38a2fb439576d2910375f8_187.png)

## 概率查询：联合分布与边际分布

![](img/bb670bc78b38a2fb439576d2910375f8_189.png)

![](img/bb670bc78b38a2fb439576d2910375f8_191.png)

网络建立后，我们可以进行各种概率查询。首先，让我们看看整个联合概率分布。

![](img/bb670bc78b38a2fb439576d2910375f8_193.png)

![](img/bb670bc78b38a2fb439576d2910375f8_195.png)

![](img/bb670bc78b38a2fb439576d2910375f8_196.png)

```r
# 查询所有变量的完整联合概率分布
joint_dist <- querygrain(GN1, type = "joint")
print(joint_dist)
```
对于四个变量，手动计算联合分布非常困难，但计算机可以轻松完成。输出结果是一个多维数组，展示了所有变量每一种可能状态组合的概率。例如，我们可以查看到“温度低于40度、下雨、没穿外套且雨伞关闭”这种极端情况的概率几乎为0。

![](img/bb670bc78b38a2fb439576d2910375f8_198.png)

![](img/bb670bc78b38a2fb439576d2910375f8_199.png)

![](img/bb670bc78b38a2fb439576d2910375f8_200.png)

![](img/bb670bc78b38a2fb439576d2910375f8_202.png)

![](img/bb670bc78b38a2fb439576d2910375f8_203.png)

然而，我们通常更关心某个特定变量的分布。这时，我们需要计算边际概率。

![](img/bb670bc78b38a2fb439576d2910375f8_205.png)

![](img/bb670bc78b38a2fb439576d2910375f8_207.png)

```r
# 计算‘外套’变量的边际概率分布
marginal_jacket <- querygrain(GN1, nodes = "jacket", type = "marginal")
print(marginal_jacket)

![](img/bb670bc78b38a2fb439576d2910375f8_208.png)

![](img/bb670bc78b38a2fb439576d2910375f8_210.png)

![](img/bb670bc78b38a2fb439576d2910375f8_211.png)

![](img/bb670bc78b38a2fb439576d2910375f8_212.png)

# 计算‘雨伞’变量的边际概率分布
marginal_umbrella <- querygrain(GN1, nodes = "umbrella", type = "marginal")
print(marginal_umbrella)
```
根据我们的条件概率表，计算结果显示我更可能穿薄外套，并且雨伞更可能处于关闭状态。

![](img/bb670bc78b38a2fb439576d2910375f8_214.png)

![](img/bb670bc78b38a2fb439576d2910375f8_215.png)

![](img/bb670bc78b38a2fb439576d2910375f8_217.png)

## 基于证据的概率推断

![](img/bb670bc78b38a2fb439576d2910375f8_219.png)

![](img/bb670bc78b38a2fb439576d2910375f8_221.png)

推断发生在我们有证据的时候。给定一组具体的观测值（证据），我们可以推断其他事件发生的可能性。

![](img/bb670bc78b38a2fb439576d2910375f8_222.png)

![](img/bb670bc78b38a2fb439576d2910375f8_224.png)

![](img/bb670bc78b38a2fb439576d2910375f8_225.png)

![](img/bb670bc78b38a2fb439576d2910375f8_226.png)

```r
# 设置证据：假设我们观察到温度>80度且天气晴朗
GN1_evidence <- setEvidence(GN1,
                            nodes = c("temperature", "weather"),
                            states = c(">80", "sunny"))

![](img/bb670bc78b38a2fb439576d2910375f8_228.png)

![](img/bb670bc78b38a2fb439576d2910375f8_229.png)

![](img/bb670bc78b38a2fb439576d2910375f8_231.png)

![](img/bb670bc78b38a2fb439576d2910375f8_233.png)

![](img/bb670bc78b38a2fb439576d2910375f8_234.png)

# 获取当前设置的证据，以确认其已被使用
getEvidence(GN1_evidence)

![](img/bb670bc78b38a2fb439576d2910375f8_236.png)

![](img/bb670bc78b38a2fb439576d2910375f8_238.png)

![](img/bb670bc78b38a2fb439576d2910375f8_239.png)

# 在给定证据的条件下，重新计算‘外套’的边际概率
marginal_jacket_given_evidence <- querygrain(GN1_evidence, nodes = "jacket", type = "marginal")
print(marginal_jacket_given_evidence)
```
设置证据后，`外套`的边际概率发生了显著变化。在没有证据时，穿薄外套的概率可能最高；但在证据（高温晴天）条件下，不穿任何外套的概率跃升至93%。这展示了贝叶斯网络如何根据新信息动态更新概率，使其在研究中非常有用。

![](img/bb670bc78b38a2fb439576d2910375f8_241.png)

![](img/bb670bc78b38a2fb439576d2910375f8_242.png)

![](img/bb670bc78b38a2fb439576d2910375f8_243.png)

![](img/bb670bc78b38a2fb439576d2910375f8_244.png)

## 关于无向图模型的说明

![](img/bb670bc78b38a2fb439576d2910375f8_246.png)

![](img/bb670bc78b38a2fb439576d2910375f8_248.png)

![](img/bb670bc78b38a2fb439576d2910375f8_249.png)

在查看网络摘要时，你可能会看到“compiled: FALSE, propagated: FALSE”的信息。这涉及到处理大型网络时的高效算法。除了有向无环图，我们还可以创建无向图独立性网络（UG）。无向图类似于马尔可夫毯，能利用图结构高效地传播概率，从而更快地计算边际分布等。当网络非常庞大，并且可以分解为不同的簇和团时，使用无向图的优势就会体现出来。对于本教程的小型网络，两种方法的结果是一致的。

![](img/bb670bc78b38a2fb439576d2910375f8_250.png)

![](img/bb670bc78b38a2fb439576d2910375f8_252.png)

![](img/bb670bc78b38a2fb439576d2910375f8_253.png)

![](img/bb670bc78b38a2fb439576d2910375f8_254.png)

## 总结

![](img/bb670bc78b38a2fb439576d2910375f8_256.png)

![](img/bb670bc78b38a2fb439576d2910375f8_257.png)

在本教程中，我们一起学习了在R中构建概率图模型的完整流程：
1.  使用`CPT`函数定义变量及其条件概率表。
2.  将变量编译成概率列表并构建贝叶斯网络。
3.  可视化网络结构。
4.  进行联合概率和边际概率查询。
5.  引入证据，并基于新证据进行概率推断。

![](img/bb670bc78b38a2fb439576d2910375f8_258.png)

![](img/bb670bc78b38a2fb439576d2910375f8_259.png)

![](img/bb670bc78b38a2fb439576d2910375f8_260.png)

![](img/bb670bc78b38a2fb439576d2910375f8_262.png)

![](img/bb670bc78b38a2fb439576d2910375f8_264.png)

你可以利用提供的代码框架，解决本模块中的练习问题。希望你能享受编码的乐趣，学习愉快！