

## 多模态深度学习

- 双模态 DBN：对每个模态，在预训练层之上逐层贪心训练一个 RBM；通过学习到的多层表示来表示数据，模型可以更容易地学习跨模态的高阶相关性。在 (d) 中，第一层表示对应音素和视位，第二层对它们之间的关系进行建模。

- 问题
  - 模型可能找到这样的表示：某些隐藏单元只针对音频，而另一些只针对视频
  - 它不适用于交叉模态学习场景，即在监督训练和测试时仅存在一种模态。

![](img/a04b187c89c5018c5ef6132980e27196_121_0.png)

(d) 双模态 DBN

## 多模态深度自编码器

- 在 (a) 中，深度自编码器被训练为在仅给定视频数据时重建两种模态，从而发现跨模态的相关性。
- 用双模态 DBN 的权重初始化深度自编码器，并丢弃任何不再存在的权重。中间层可用作新的特征表示。
- 当监督训练和测试时仅存在单一模态时，使用模型 (a)

![](img/a04b187c89c5018c5ef6132980e27196_122_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_122_1.png)

## 多模态深度自编码器

用于图像分割：Luo 等人，CVPR'12

![](img/a04b187c89c5018c5ef6132980e27196_124_0.png)

## 阅读材料

- G. E. Hinton 和 R. R. Salakhutdinov，“Reducing the Dimensionality of Data with Neural Networks，”Science，第 313 卷，第 504-507 页，2006 年 7 月。
- K. Kavukcuoglu、M. Ranzato 和 Y. LeCun，“Fast Inference in Sparse Coding Algorithms with Applications to Object Recognition，”CBLL-TR-2008-12-01，NYU，2008 年。
- J. Ngiam、A. Khosla、M. Kim、J. Nam、H. Lee 和 A. Y. Ng，“Multimodal Deep Learning，”ICML 2011。
- P. Luo、X. Wang 和 X. Tang，“Hierarchical Face Parsing via Deep Learning，”CVPR 2012。

## 大纲

- 1. HMM
  - 马尔可夫模型
  - 隐马尔可夫模型
- 2. 循环神经网络
  - 循环神经网络
  - 基于 RNN 的 BP
  - RNN 的变体
- 3. 长短期记忆循环网络
  - 长期依赖的挑战
  - 结合短路径和长路径
  - 长短期记忆网络
- 4. 应用

## 对序列数据建模

- 从某个分布中对数据序列进行采样
  $P(x_1,\dots,x_T)$
- 生成自然语句来描述图像
  $P(y_1,\dots,y_T\mid I)$
- 从视频序列中进行活动识别
  $P(y\mid x_1,\dots,x_T)$

![](img/a04b187c89c5018c5ef6132980e27196_129_0.png)

## 对序列数据建模

- 生成自然语句来描述视频
  $P(Y_1,\dots,Y_T \mid X_1,\dots,X_T)$
- 语言翻译
  $P(Y_1,\dots,Y_T \mid X_1,\dots,X_T)$

Ulrich UNK，奥迪汽车制造商董事会成员，声称多年来在董事会会议之前收集手机以防止它们被用作远程监听设备已成为一种常见做法。

Ulrich Hackenberg，奥迪汽车制造商董事会成员，声明在董事会会议之前收集手机以防止它们被用作远程监听设备，多年来一直是一种常见做法。

## 对序列数据建模

- 使用链式法则来表示观测序列的联合分布
  $p(\mathbf{x}_1,\dots,\mathbf{x}_T)=\prod_{t=1}^{T} p(\mathbf{x}_t|\mathbf{x}_1,\dots,\mathbf{x}_{t-1})$

- 考虑未来观测对所有先前观测的一般依赖性是不切实际的 $p(\mathbf{x}_t|\mathbf{x}_{t-1},\dots,\mathbf{x}_0)$

- 随着观测数量的增加，复杂度将无限增长

- 在预测未来值时，可以预期最近的观测比更久远的观测提供更多信息

