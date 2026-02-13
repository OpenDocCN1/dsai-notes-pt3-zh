# P145：L17.7 - PyTorch 中的 VAE 潜在空间算法 🎭

在本节课中，我们将学习如何操作变分自编码器（VAE）的潜在空间，通过简单的向量运算来修改生成图像的属性，例如让人物微笑或戴上眼镜。

![](img/ee666c6018756e5084ebb2ab7329b7da_1.png)

---

## 📋 概述

![](img/ee666c6018756e5084ebb2ab7329b7da_3.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_5.png)

上一节我们介绍了VAE的构建与训练。本节中，我们将探索一个有趣的应用：潜在空间算术。我们将利用在CelebA人脸数据集上训练好的VAE模型，通过计算并操作潜在空间中的向量，来修改生成图像的面部属性。

![](img/ee666c6018756e5084ebb2ab7329b7da_7.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_9.png)

## 🧠 核心概念：潜在空间算术

![](img/ee666c6018756e5084ebb2ab7329b7da_11.png)

其核心思想是，在训练好的VAE的潜在空间中，不同的方向可能对应着不同的语义特征。我们可以通过计算代表特定属性（如“微笑”）的向量，并将其添加到某张图像的潜在编码中，从而修改生成的图像。

**核心公式**可以表示为：
`新潜在向量 = 原始潜在向量 + α * (微笑向量 - 非微笑向量)`
其中，`α` 是一个缩放超参数，控制属性修改的强度。

## 🔧 实现步骤详解

![](img/ee666c6018756e5084ebb2ab7329b7da_13.png)

以下是实现潜在空间属性操作的主要步骤。

### 第一步：计算属性向量

我们需要分别计算“微笑”和“非微笑”图像在潜在空间中的平均向量。

```python
# 伪代码示意
def compute_average_faces(images, labels, feature_index, encoder):
    # 初始化累加器
    avg_with_feature = 0
    avg_without_feature = 0
    count_with = 0
    count_without = 0

    for batch_images, batch_labels in dataloader:
        # 获取当前批次图像的潜在编码
        embeddings = encoder(batch_images) if encoder else batch_images

        # 根据标签筛选具有特定属性的图像
        has_feature_mask = batch_labels[:, feature_index] == 1
        embeddings_with_feature = embeddings[has_feature_mask]
        embeddings_without_feature = embeddings[~has_feature_mask]

        # 分别累加
        avg_with_feature += embeddings_with_feature.sum(dim=0)
        avg_without_feature += embeddings_without_feature.sum(dim=0)
        count_with += len(embeddings_with_feature)
        count_without += len(embeddings_without_feature)

    # 计算平均值
    smile_vector = avg_with_feature / count_with
    no_smile_vector = avg_without_feature / count_without

    return smile_vector, no_smile_vector
```

### 第二步：计算差异向量并应用

![](img/ee666c6018756e5084ebb2ab7329b7da_15.png)

得到平均向量后，我们计算它们的差值，这个差值向量就指向了从“非微笑”到“微笑”的方向。

```python
# 计算微笑差异向量
smile_vector, no_smile_vector = compute_average_faces(..., feature_index=31, ...) # 31对应微笑属性
difference_vector = smile_vector - no_smile_vector

![](img/ee666c6018756e5084ebb2ab7329b7da_17.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_19.png)

# 对单张图像进行操作
original_image = ...
original_latent = encoder(original_image)

![](img/ee666c6018756e5084ebb2ab7329b7da_21.png)

# 应用潜在空间算术
alpha = 2.0  # 控制微笑程度
new_latent = original_latent + alpha * difference_vector

# 通过解码器生成新图像
modified_image = decoder(new_latent)
```

![](img/ee666c6018756e5084ebb2ab7329b7da_23.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_25.png)

### 第三步：可视化结果

![](img/ee666c6018756e5084ebb2ab7329b7da_27.png)

我们将原始图像、修改后的图像以及不同`α`值下的效果进行对比展示。

## 🖼️ 效果对比：原始空间 vs 潜在空间

在深入代码前，理解为何要在潜在空间而非原始像素空间进行操作很重要。

*   **原始像素空间操作**：直接计算所有微笑/非微笑人像的平均像素图像，然后将差值加到目标图像上。这种方法有时有效，但通常会产生模糊、不自然的结果，因为它混合了不同图像的所有细节。
*   **潜在空间操作**：VAE的潜在空间是一个结构化的、连续的表示空间。在此空间进行算术运算，能更好地保持图像的身份和自然度，仅改变目标属性，通常能产生更清晰、更可控的效果。

![](img/ee666c6018756e5084ebb2ab7329b7da_29.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_31.png)

## 💻 代码实践与结果

![](img/ee666c6018756e5084ebb2ab7329b7da_33.png)

现在，让我们加载训练好的VAE模型，并实际运行上述步骤。

首先，我们计算潜在空间中的微笑向量和非微笑向量。

```python
# 加载预训练模型和数据
model = load_pretrained_vae()
dataloader, labels = load_celeba_data()

# 计算潜在空间中的平均向量
smile_vec, no_smile_vec = compute_average_faces(
    dataloader, labels, feature_index=31, encoder=model.encoder
)
diff_vec = smile_vec - no_smile_vec
```

![](img/ee666c6018756e5084ebb2ab7329b7da_35.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_36.png)

接着，我们选取一张测试图像，通过调整`α`值来改变其微笑程度。

```python
# 选取一张图像
test_img, _ = next(iter(dataloader))
test_img = test_img[0:1]  # 取第一张

![](img/ee666c6018756e5084ebb2ab7329b7da_38.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_40.png)

# 编码到潜在空间
z_original = model.encoder(test_img)

![](img/ee666c6018756e5084ebb2ab7329b7da_42.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_43.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_45.png)

# 尝试不同的alpha值
alphas = [-3, -1.5, 0, 1.5, 3]
modified_images = []
for alpha in alphas:
    z_new = z_original + alpha * diff_vec
    img_new = model.decoder(z_new)
    modified_images.append(img_new)

# 绘制结果
plot_images([test_img] + modified_images, titles=[‘Original’] + [f‘Alpha={a}’ for a in alphas])
```

![](img/ee666c6018756e5084ebb2ab7329b7da_47.png)

运行上述代码后，你将看到随着`α`值增大，生成图像中人物的微笑变得更加明显；当`α`为负值时，微笑则会减弱。

![](img/ee666c6018756e5084ebb2ab7329b7da_49.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_50.png)

同样的方法可以应用于其他属性，例如“戴眼镜”（对应特定的属性索引）。只需更改`feature_index`，即可尝试让人物戴上或摘下眼镜。

## 📝 总结

![](img/ee666c6018756e5084ebb2ab7329b7da_52.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_53.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_54.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_55.png)

本节课中我们一起学习了VAE潜在空间算术。我们了解到，通过计算潜在空间中代表特定语义属性的方向向量，并对其进行简单的加减运算，我们可以有目的地、连续地控制生成图像的属性。这种方法比在原始像素空间操作更加强大和有效，展示了学习到的潜在表示的结构化特性。

![](img/ee666c6018756e5084ebb2ab7329b7da_57.png)

![](img/ee666c6018756e5084ebb2ab7329b7da_59.png)

在下一讲中，我们将探讨另一种重要的生成模型：生成对抗网络（GAN）。