# 23：HW10 - Diffusion模型定制化教程 🎨

![](img/c8b37866b5adabcafc7bd9f11ed28987_1.png)

在本节课中，我们将学习如何完成作业十（HW10），其核心主题是**文本到图像扩散模型（Text-to-Image Diffusion Model）的定制化（Customization）**。我们将理解任务目标、评分标准，并实践两种关键方法来实现特定对象的个性化图像生成。

![](img/c8b37866b5adabcafc7bd9f11ed28987_3.png)

---

## 概述

本次作业的目标是让扩散模型能够根据给定的文本提示（Prompt）生成图像，同时确保图像中的特定对象与提供的参考图像（Reference Image）保持一致。例如，给定一张宠物狗的照片和提示“a dog in a bad man suit”，模型需要生成一张穿着坏蛋套装的狗的照片，并且这只狗必须是参考图像中的那一只。

![](img/c8b37866b5adabcafc7bd9f11ed28987_5.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_7.png)

普通文本到图像模型的问题是，每次生成的“狗”可能都不同。本任务旨在解决这个问题，实现**对象一致性**的定制化生成。

---

## 任务与评分标准

![](img/c8b37866b5adabcafc7bd9f11ed28987_9.png)

我们将获得多张特定对象的参考图像和一个文本提示。目标是生成一系列既符合文本描述，其主体对象又与参考图像相似的图片。

评分基于两个自动化指标：

![](img/c8b37866b5adabcafc7bd9f11ed28987_11.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_13.png)

1.  **DINO Score**：衡量生成图像中的对象与参考图像的视觉相似度。
    *   **公式**：`similarity = cosine_similarity(DINO_encoder(reference_img), DINO_encoder(generated_img))`
    *   分数越高，表示对象越像。

![](img/c8b37866b5adabcafc7bd9f11ed28987_15.png)

2.  **CLIP Score**：衡量生成图像与给定文本提示的相关性。
    *   **公式**：`similarity = cosine_similarity(CLIP_text_encoder(text_prompt), CLIP_image_encoder(generated_img))`
    *   分数越高，表示图像与文本描述越匹配。

作业包含6个对象，每个对象成功定制化（即两个分数均达到阈值）可得1分，总计6分。

---

## 核心方法介绍

上一节我们明确了任务目标和评分标准。本节中，我们来看看实现定制化的两种核心方法。

### 方法一：Custom Diffusion

此方法的核心思想是通过**微调（Fine-tuning）**，让模型学会一个代表特定对象的新词（Token），例如“<new1>”。

**流程如下**：
1.  输入参考图像。
2.  在微调过程中，训练模型理解当看到“<new1>”这个Token时，就应该生成具有参考图像特征的对象。
3.  推理时，使用如“a <new1> dog in a bucket”的提示，模型就能生成与参考图像一致的、在桶里的狗。

这种方法效果较好，但每个新对象都需要进行一次微调，比较耗时。

### 方法二：BLIP-Diffusion

![](img/c8b37866b5adabcafc7bd9f11ed28987_17.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_19.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_21.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_23.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_25.png)

此方法旨在改进Custom Diffusion需要反复微调的缺点。其核心思想是训练一个**额外的模型**，能够根据输入的参考图像，直接预测出对应的特殊Token（如“<new1>”）。

![](img/c8b37866b5adabcafc7bd9f11ed28987_27.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_29.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_30.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_32.png)

**流程如下**：
1.  将参考图像输入一个预训练好的编码器模型。
2.  该模型输出一个代表此参考图像的特定Token嵌入（Embedding）。
3.  将此Token嵌入与文本提示一起输入到文本到图像扩散模型中，即可生成定制化的图像。

![](img/c8b37866b5adabcafc7bd9f11ed28987_34.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_36.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_38.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_40.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_42.png)

这种方法无需微调扩散模型本身，因此速度更快，更方便。

![](img/c8b37866b5adabcafc7bd9f11ed28987_44.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_46.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_48.png)

---

![](img/c8b37866b5adabcafc7bd9f11ed28987_50.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_52.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_54.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_56.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_58.png)

## 作业数据与参数调优建议

![](img/c8b37866b5adabcafc7bd9f11ed28987_60.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_62.png)

本次作业的数据集包含6个对象（如猫、狗、太阳镜等），每个对象有对应的参考图像和需要生成的文本提示。

![](img/c8b37866b5adabcafc7bd9f11ed28987_64.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_66.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_68.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_70.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_72.png)

为了获得更好的分数，你需要调整模型的一些超参数。以下是针对两种方法的调优建议：

![](img/c8b37866b5adabcafc7bd9f11ed28987_74.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_76.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_78.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_80.png)

**对于BLIP-Diffusion方法，主要调整以下两个参数：**
*   `num_inference_steps`：去噪步数。增加步数通常能提升图像质量，但会减慢生成速度。建议尝试范围：**100~200**。
*   `guidance_scale`：指导尺度。控制生成结果与文本提示的关联程度。值太高可能导致图像出现伪影。建议尝试范围：**7.5~15**。

![](img/c8b37866b5adabcafc7bd9f11ed28987_82.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_84.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_86.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_88.png)

**对于Custom Diffusion方法，主要调整训练相关参数：**
*   `instance_prompt`：实例提示。这是微调时使用的文本，**必须包含“<new1>”这类特殊Token**，并尽可能详细地描述对象（如“a black <new1> dog”）。
*   `parameters_to_train`：选择微调模型的哪些部分。微调更多参数（如Q、K、V）会使生成对象更像参考图，但可能削弱对文本的遵循能力。

![](img/c8b37866b5adabcafc7bd9f11ed28987_90.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_92.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_94.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_96.png)

---

![](img/c8b37866b5adabcafc7bd9f11ed28987_98.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_100.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_102.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_104.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_106.png)

## 代码执行与提交规范

![](img/c8b37866b5adabcafc7bd9f11ed28987_108.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_110.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_112.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_114.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_116.png)

我们将使用提供的Colab示例代码进行实践。代码已实现上述两种方法。

![](img/c8b37866b5adabcafc7bd9f11ed28987_118.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_120.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_122.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_124.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_126.png)

**执行步骤概述：**
1.  在Colab中复制提供的笔记。
2.  确保运行时类型设置为GPU。
3.  根据需要运行BLIP-Diffusion或Custom Diffusion的代码块。
4.  调整超参数，生成图像。

![](img/c8b37866b5adabcafc7bd9f11ed28987_128.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_130.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_132.png)

**提交包含两部分：**
1.  **代码提交（占4分）**：将最终代码打包成ZIP文件，按要求命名并提交至课程系统。压缩包内应包含`report.pdf`和所有源代码。
2.  **结果提交（占6分）**：将生成的图像打包成ZIP文件提交。压缩包内必须包含名为`object1`到`object6`的6个文件夹，每个文件夹下包含15张分辨率为512x512的图片（如`0.jpg`到`14.jpg`）。

![](img/c8b37866b5adabcafc7bd9f11ed28987_134.png)

请务必遵守学术诚信规定，不要使用额外数据或分享代码。

![](img/c8b37866b5adabcafc7bd9f11ed28987_136.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_138.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_140.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_142.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_144.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_146.png)

---

![](img/c8b37866b5adabcafc7bd9f11ed28987_148.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_150.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_151.png)

## 总结

![](img/c8b37866b5adabcafc7bd9f11ed28987_153.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_155.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_157.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_159.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_161.png)

本节课中，我们一起学习了扩散模型定制化的任务。
我们理解了通过**DINO Score**和**CLIP Score**来评估生成效果的标准。
我们掌握了两种实现定制化的关键技术：需要微调的 **Custom Diffusion** 和更高效的 **BLIP-Diffusion**。
最后，我们了解了作业的数据结构、参数调优方向以及具体的代码执行与提交规范。

![](img/c8b37866b5adabcafc7bd9f11ed28987_163.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_165.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_167.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_168.png)

通过完成本作业，你将能够实践如何让AI模型根据你的想法，生成既富有创意又保持特定对象一致性的图像。