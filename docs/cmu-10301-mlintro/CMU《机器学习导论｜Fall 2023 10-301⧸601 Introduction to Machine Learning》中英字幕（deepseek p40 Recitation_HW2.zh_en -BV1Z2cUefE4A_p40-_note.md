# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p40 Recitation_HW2.zh_en -BV1Z2cUefE4A_p40-

![](img/cfb8fc811311cce0a32c27eb65612cf8_1.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_3.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_5.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_7.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_9.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_11.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_13.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_15.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_17.png)

## 1. 树结构简介

![](img/cfb8fc811311cce0a32c27eb65612cf8_19.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_21.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_23.png)

大家好，欢迎来到课堂。这是第二次复习课和这次作业。

![](img/cfb8fc811311cce0a32c27eb65612cf8_25.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_27.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_28.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_29.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_31.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_33.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_35.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_36.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_37.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_39.png)

正如你们所知，这次作业是关于决策树的。所以我们将从树结构和算法的简介开始。😊。

### 1.1 树的深度

![](img/cfb8fc811311cce0a32c27eb65612cf8_41.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_43.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_45.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_47.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_48.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_50.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_51.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_53.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_54.png)

树的深度是指从根节点到最远叶子节点的最长路径的长度。我们可以通过计算路径上的边数来确定长度。

![](img/cfb8fc811311cce0a32c27eb65612cf8_56.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_58.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_60.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_62.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_64.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_66.png)

### 1.2 节点的深度

![](img/cfb8fc811311cce0a32c27eb65612cf8_68.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_69.png)

节点的深度与树的深度类似，它是从根节点到给定节点的路径长度。

![](img/cfb8fc811311cce0a32c27eb65612cf8_71.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_73.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_75.png)

### 1.3 练习

![](img/cfb8fc811311cce0a32c27eb65612cf8_77.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_79.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_81.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_83.png)

以下是几个关于树深度的练习：

![](img/cfb8fc811311cce0a32c27eb65612cf8_85.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_86.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_88.png)

- 树A的深度是多少？
- 节点x4的深度是多少？
- 树B的深度是多少？
- 树C的深度是多少？

![](img/cfb8fc811311cce0a32c27eb65612cf8_90.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_92.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_94.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_96.png)

## 2. 树遍历

![](img/cfb8fc811311cce0a32c27eb65612cf8_98.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_99.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_101.png)

树遍历是指以特定顺序访问树中的所有节点。

![](img/cfb8fc811311cce0a32c27eb65612cf8_103.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_104.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_105.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_107.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_109.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_111.png)

### 2.1 遍历方法

![](img/cfb8fc811311cce0a32c27eb65612cf8_113.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_114.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_116.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_118.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_119.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_121.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_122.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_124.png)

以下是三种常见的树遍历方法：

![](img/cfb8fc811311cce0a32c27eb65612cf8_126.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_128.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_130.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_132.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_134.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_135.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_136.png)

- **前序遍历**：先访问根节点，然后遍历左子树，最后遍历右子树。
- **中序遍历**：先遍历左子树，然后访问根节点，最后遍历右子树。
- **后序遍历**：先遍历左子树，然后遍历右子树，最后访问根节点。

![](img/cfb8fc811311cce0a32c27eb65612cf8_138.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_140.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_142.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_143.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_144.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_145.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_146.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_147.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_149.png)

## 3. 互信息

![](img/cfb8fc811311cce0a32c27eb65612cf8_151.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_153.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_154.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_155.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_156.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_158.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_160.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_162.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_164.png)

互信息是衡量两个随机变量之间相关性的指标。

![](img/cfb8fc811311cce0a32c27eb65612cf8_166.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_167.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_169.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_170.png)

### 3.1 互信息的定义

![](img/cfb8fc811311cce0a32c27eb65612cf8_172.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_173.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_174.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_175.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_176.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_177.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_178.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_179.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_181.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_183.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_185.png)

互信息 \( I(X;Y) \) 等于 \( H(Y) - H(Y|X) \)，其中 \( H(Y) \) 是 \( Y \) 的熵，\( H(Y|X) \) 是 \( Y \) 在 \( X \) 的条件下的熵。

![](img/cfb8fc811311cce0a32c27eb65612cf8_187.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_189.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_191.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_193.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_195.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_197.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_198.png)

### 3.2 互信息的计算

![](img/cfb8fc811311cce0a32c27eb65612cf8_200.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_202.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_204.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_206.png)

以下是计算互信息的步骤：

![](img/cfb8fc811311cce0a32c27eb65612cf8_208.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_209.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_211.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_213.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_215.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_217.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_219.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_220.png)

1. 计算 \( H(Y) \) 和 \( H(Y|X) \)。
2. 计算 \( I(X;Y) = H(Y) - H(Y|X) \)。

![](img/cfb8fc811311cce0a32c27eb65612cf8_222.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_224.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_226.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_227.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_228.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_229.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_230.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_231.png)

## 4. 决策树构建

![](img/cfb8fc811311cce0a32c27eb65612cf8_233.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_234.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_235.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_237.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_239.png)

决策树是一种基于数据的分类算法。

![](img/cfb8fc811311cce0a32c27eb65612cf8_240.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_242.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_244.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_245.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_247.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_249.png)

### 4.1 决策树构建步骤

![](img/cfb8fc811311cce0a32c27eb65612cf8_251.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_253.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_255.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_257.png)

1. 计算目标变量 \( Y \) 和每个特征 \( X_i \) 之间的互信息。
2. 选择互信息最大的特征 \( X_i \) 作为分裂特征。
3. 根据特征 \( X_i \) 的值将数据集划分为子集。
4. 递归地对每个子集重复步骤 1-3，直到满足停止条件。

![](img/cfb8fc811311cce0a32c27eb65612cf8_259.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_261.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_263.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_264.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_266.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_268.png)

### 4.2 停止条件

![](img/cfb8fc811311cce0a32c27eb65612cf8_270.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_272.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_274.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_276.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_278.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_280.png)

以下是常见的停止条件：

![](img/cfb8fc811311cce0a32c27eb65612cf8_282.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_284.png)

- 达到最大深度。
- 节点是纯的（即所有数据都属于同一类别）。

![](img/cfb8fc811311cce0a32c27eb65612cf8_286.png)

## 5. 编程技巧

![](img/cfb8fc811311cce0a32c27eb65612cf8_288.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_289.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_291.png)

以下是构建决策树时的一些编程技巧：

![](img/cfb8fc811311cce0a32c27eb65612cf8_293.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_294.png)

- 使用 Python 的 PDB 调试器进行调试。
- 使用 print 调试来检查变量的值。
- 避免在测试数据上重新训练模型。

![](img/cfb8fc811311cce0a32c27eb65612cf8_296.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_297.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_298.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_300.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_302.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_304.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_306.png)

## 总结

![](img/cfb8fc811311cce0a32c27eb65612cf8_308.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_310.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_312.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_314.png)

本节课中，我们学习了决策树的基本概念、树遍历方法、互信息以及决策树构建步骤。希望这些知识能够帮助你们完成作业。