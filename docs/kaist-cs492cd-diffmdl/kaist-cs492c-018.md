# 扩散模型和应用：P18：嘉宾讲座2 - Jiaming Song - Dream Machine：视频基础模型 🎬

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_0.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_2.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_4.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_6.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_7.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_8.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_9.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_10.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_12.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_14.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_15.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_16.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_17.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_18.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_20.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_21.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_22.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_23.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_25.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_26.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_28.png)

在本节课中，我们将学习Luma AI公司开发的Dream Machine视频生成模型。我们将探讨其背后的技术原理，特别是如何利用大规模视频数据训练模型，使其具备理解深度、光影、物理动态乃至因果关系的“涌现”能力。课程将从公司背景、技术挑战讲起，逐步深入到扩散模型、注意力机制以及视频模型在3D/4D生成中的应用前景。

---

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_30.png)

## 公司背景与动机 🏢

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_32.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_34.png)

上一节我们介绍了Dream Machine生成的令人印象深刻的视频。本节中，我们来看看开发该模型的Luma AI公司的背景及其转向视频模型的动机。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_36.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_38.png)

Luma最初致力于3D内容创作，例如场景捕捉（Scene Capture）和3D生成工具Genie。这些技术依赖于多视角图像重建（如NeRF、Gaussian Splatting）来创建交互式3D内容。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_40.png)

然而，团队很快意识到3D数据存在根本性的可扩展性问题。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_42.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_44.png)

以下是3D数据与图像/视频数据的对比：

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_46.png)

*   **数据规模与质量**：图像和视频数据在互联网上极为丰富。例如，用于训练Stable Diffusion的LAION数据集包含约50亿张图像。而最大的3D数据集之一ObjectVerse仅宣称有1000万个物体，且经过质量过滤后数量更少。3D数据不仅稀缺，质量也参差不齐。
*   **数据创建难度**：用手机拍摄图像或视频非常容易。但创建3D数据需要专业设备、人工采集（如雇佣人员多角度扫描物体）或艺术家创作，过程复杂且成本高昂。
*   **算法可扩展性**：当前的3D重建算法（如NeRF）需要对每个场景进行独立的优化求解，这个过程计算密集，难以规模化。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_48.png)

因此，尽管3D生成需求明确，但数据和算法的限制使得纯3D路径难以实现大规模突破。这促使Luma将目光投向了视频。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_50.png)

---

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_52.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_54.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_55.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_56.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_57.png)

## 核心AI范式：从自回归到扩散模型 🤖

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_59.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_60.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_61.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_62.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_63.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_65.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_66.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_67.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_68.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_69.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_70.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_71.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_72.png)

在深入视频模型之前，我们需要理解当前生成式AI的两大核心范式。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_74.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_76.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_77.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_78.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_80.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_82.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_83.png)

**自回归模型**（如大型语言模型LLM）通过“预测下一个词元（token）”来学习。其公式可以简化为：
`P(x_t | x_<t)`，即在给定前文序列 `x_<t` 的条件下，预测下一个词元 `x_t` 的概率分布。虽然自回归在文本上取得了巨大成功，但对于图像、视频等连续信号，其表现通常不如扩散模型。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_85.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_86.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_87.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_88.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_89.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_90.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_91.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_92.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_93.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_95.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_97.png)

**扩散模型**提供了一种可扩展的替代方案。其核心思想是学习一个去噪过程。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_99.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_100.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_101.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_102.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_103.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_104.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_105.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_106.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_107.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_109.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_110.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_111.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_112.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_113.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_115.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_116.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_117.png)

1.  **前向过程（加噪）**：从一张干净图像 `x_0` 开始，逐步添加高斯噪声，经过 `T` 步后得到纯噪声 `x_T`。
    `x_t = sqrt(alpha_t) * x_0 + sqrt(1 - alpha_t) * epsilon`, 其中 `epsilon ~ N(0, I)`
2.  **反向过程（去噪）**：模型学习从噪声 `x_t` 中预测出干净图像 `x_0`（或直接预测所添加的噪声 `epsilon`）。模型在训练时知道当前的噪声水平 `t`，从而在不同噪声强度下进行去噪。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_119.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_121.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_123.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_124.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_125.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_126.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_128.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_129.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_130.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_132.png)

扩散模型通过解决这个去噪任务，避免了自回归模型在连续数据上离散化的困难，被证明是图像和视频生成的强大基础。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_134.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_136.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_138.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_140.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_142.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_143.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_144.png)

---

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_146.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_147.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_148.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_149.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_150.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_151.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_153.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_154.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_156.png)

## 多模态学习的基石：注意力机制 🔗

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_158.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_159.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_161.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_162.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_164.png)

扩散模型如此强大的一个关键因素是**注意力机制**，它使得模型能够学习不同模态（如文本和图像）之间的关联。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_166.png)

在一个多模态数据样本中（例如，文本“柯基犬玩喷火喇叭”和对应的图像），注意力机制的工作原理如下：
*   文本词元作为**查询（Query）**。
*   图像块作为**键（Key）**和**值（Value）**。
*   通过计算查询与键的相似度，模型可以建立文本词元与相关图像区域之间的关联。例如，“柯基犬”这个词的注意力会聚焦在图像中柯基犬所在的区域。

这种**交叉注意力**是Stable Diffusion等文生图模型的核心组件之一，它允许文本条件有效地引导图像生成。此外，**自注意力**让模型能够理解图像内部或视频帧之间的关系。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_168.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_170.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_172.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_174.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_175.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_176.png)

---

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_177.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_178.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_179.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_181.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_182.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_183.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_184.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_185.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_186.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_187.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_188.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_190.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_192.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_193.png)

## 从图像到3D：指令微调的力量 🎯

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_195.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_196.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_197.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_198.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_200.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_201.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_203.png)

我们了解到3D数据稀缺，但图像数据丰富。那么，如何利用强大的图像模型来生成3D内容呢？答案是**指令微调**。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_205.png)

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_206.png)

这个想法借鉴了大语言模型的成功经验：先在大规模、质量一般的文本数据上预训练一个基础模型，然后在较小规模、但质量更高的指令-回答数据对上对其进行微调，模型就能学会遵循指令。

将其应用到3D生成：
1.  **基础模型**：在数十亿的图文对上训练的**文生图扩散模型**（高质量，海量数据）。
2.  **微调数据**：数百万的**文本-多视角图像对**（更高质，但数据量少）。这些多视角图像可以从现有的3D数据集中渲染得到。
3.  **关键修改**：在微调时，我们将模型从生成单张图像改为同时生成多张不同视角的图像。通过**自注意力机制**和额外的**相机姿态条件**，模型学会了在不同视角间保持3D一致性。

这样，我们就将一个文生图模型，微调成了一个能生成多视角一致图像的模型。随后，利用这些多视角图像，通过传统的3D重建算法（如NeRF或基于Transformer的重建器）就能得到3D模型。

---

## Dream Machine：作为4D生成基石的视频模型 🚀

既然可以从图像扩展到3D（多视角），那么很自然地，我们可以从视频扩展到4D（3D+时间）。视频本质上是时间上的多视角序列。

Dream Machine就是一个大规模训练的视频基础模型。它不仅能生成时间上连贯的视频，还展现出许多令人惊讶的“涌现”能力，这些能力对于理解动态3D世界至关重要：

以下是Dream Machine展现出的部分涌现能力示例：

*   **深度感知**：当相机旋转时，前景物体与背景物体的运动视差符合物理规律，表明模型理解了场景的几何深度。
*   **光影与材质**：模型能模拟复杂的光线传输效果，如霓虹灯牌在人物头发上的颜色反射、透明眼镜的折射、金属表面的高光变化等。
*   **物理动态**：能够生成水花飞溅、毛发飘动、衣物模拟、烟雾扩散等复杂的动态效果。
*   **因果与叙事**：模型能在视频剪辑中保持主体一致性，并暗示不同镜头间的因果或情绪关系（如一个角色因看到某物而表现出恐惧）。
*   **长程一致性**：支持生成长达数十秒、包含复杂相机运动（如推拉、旋转）的视频，主体在过程中保持稳定。

这些能力并非通过显式编程3D物理规则获得，而是模型通过在海量视频数据上学习，内化了对世界运作方式的理解。

---

## 未来方向与开放挑战 ❓

尽管视频生成取得了巨大进展，但仍面临许多挑战和未来发展方向：

1.  **可控性**：如何让用户更精确地控制视频内容（如特定物体运动、精确相机轨迹）是一个关键问题。解决方案可能包括类似ControlNet的适配器技术，或利用合成数据（如从3D引擎渲染的视频）进行微调。
2.  **模型架构探索**：结合自回归与扩散模型优势的混合模型（如Diffusion Transformers）、考虑视觉多尺度特性的自回归模型、以及扩散掩码生成（Diffusion Forcing）等都是有趣的研究方向。
3.  **物理准确性**：当前模型在复杂物理交互（如物体碰撞、阴影精确移动）上仍会出错。解决之道可能在于更大规模的数据训练、结合物理模拟的合成数据，或改进的训练目标。
4.  **Janus（多面）问题**：与文生3D中的问题类似，视频模型有时会在物体上生成多个正面，这是视角先验偏差导致的，需要通过数据或训练技巧来缓解。
5.  **通向4D生成**：视频模型是通往4D生成（动态3D场景）的可行路径。通过在多视角视频数据集（如Ego-Exo4D）上对视频模型进行指令微调，有望直接生成动态的3D内容。

![](img/bbd4b3f0a6f1dd2af947c4498cdf34f2_208.png)

---

## 总结 📝

本节课我们一起学习了Luma AI的Dream Machine视频生成模型。我们从3D数据稀缺的挑战出发，回顾了扩散模型和注意力机制的核心原理。我们重点探讨了如何通过“指令微调”策略，将海量图像数据上训练的知识迁移到3D/视频生成任务中。Dream Machine作为一个视频基础模型，展现出了深度、光影、物理动态等多方面的涌现能力，证明了从视频数据学习是构建理解动态世界AI系统的可扩展路径。最后，我们探讨了该领域在可控性、物理准确性等方面面临的挑战以及未来的研究方向。视频生成模型正在快速发展，它不仅是一个创意工具，更是我们构建更通用、更理解物理世界AI智能体的重要基石。