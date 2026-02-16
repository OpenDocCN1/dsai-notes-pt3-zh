# 143：L17.5 - PyTorch 中手写数字的变分自动编码器 🧠

![](img/571a6f32a80cb0c70d0d2b425fa84956_1.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_2.png)

在本节课中，我们将要学习如何使用PyTorch为MNIST手写数字数据集构建一个变分自动编码器。我们将从最简单的卷积结构开始，逐步理解VAE的核心组件，包括编码器、重参数化技巧以及损失函数的计算。

---

![](img/571a6f32a80cb0c70d0d2b425fa84956_4.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_5.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_6.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_7.png)

## 概述与准备工作

![](img/571a6f32a80cb0c70d0d2b425fa84956_9.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_10.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_12.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_13.png)

我们将从MNIST数据集开始构建一个卷积变分自动编码器。其结构与之前课程中的普通自动编码器类似，但关键区别在于我们使用均值向量和方差对数向量，并在损失函数中加入了KL散度项。

![](img/571a6f32a80cb0c70d0d2b425fa84956_15.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_17.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_18.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_20.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_22.png)

首先，我们导入必要的库并设置一些超参数。

![](img/571a6f32a80cb0c70d0d2b425fa84956_23.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_25.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_27.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_28.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_30.png)

```python
import torch
import torch.nn as nn
import torch.optim as optim
from torchvision import datasets, transforms

![](img/571a6f32a80cb0c70d0d2b425fa84956_32.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_33.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_35.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_37.png)

# 超参数设置
batch_size = 256
learning_rate = 0.0005
epochs = 50
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
```

![](img/571a6f32a80cb0c70d0d2b425fa84956_39.png)

接下来，我们加载MNIST数据集。由于变分自动编码器是无监督模型，我们只需要图像数据，不需要标签。

```python
# 数据加载
transform = transforms.Compose([transforms.ToTensor()])
train_dataset = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
train_loader = torch.utils.data.DataLoader(dataset=train_dataset, batch_size=batch_size, shuffle=True)
```

![](img/571a6f32a80cb0c70d0d2b425fa84956_41.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_43.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_45.png)

---

![](img/571a6f32a80cb0c70d0d2b425fa84956_47.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_49.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_51.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_53.png)

## 构建VAE模型 🏗️

![](img/571a6f32a80cb0c70d0d2b425fa84956_54.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_56.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_58.png)

上一节我们介绍了数据准备，本节中我们来看看模型的核心结构。我们的VAE模型包含一个编码器和一个解码器。

![](img/571a6f32a80cb0c70d0d2b425fa84956_60.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_61.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_63.png)

以下是模型的定义，我们使用卷积层进行编码，并使用转置卷积层进行解码。

![](img/571a6f32a80cb0c70d0d2b425fa84956_65.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_67.png)

```python
class ConvVAE(nn.Module):
    def __init__(self, latent_dim=2):
        super(ConvVAE, self).__init__()
        self.latent_dim = latent_dim

        # 编码器
        self.encoder = nn.Sequential(
            nn.Conv2d(1, 32, kernel_size=3, stride=2, padding=1),  # 输出: 14x14x32
            nn.ReLU(),
            nn.Conv2d(32, 64, kernel_size=3, stride=2, padding=1), # 输出: 7x7x64
            nn.ReLU(),
            nn.Flatten(),
            nn.Linear(7*7*64, 128),
            nn.ReLU()
        )
        # 均值向量层
        self.fc_mu = nn.Linear(128, latent_dim)
        # 方差对数向量层
        self.fc_logvar = nn.Linear(128, latent_dim)

        # 解码器
        self.decoder_input = nn.Linear(latent_dim, 7*7*64)
        self.decoder = nn.Sequential(
            nn.Unflatten(1, (64, 7, 7)),
            nn.ConvTranspose2d(64, 32, kernel_size=3, stride=2, padding=1, output_padding=1), # 输出: 14x14x32
            nn.ReLU(),
            nn.ConvTranspose2d(32, 1, kernel_size=3, stride=2, padding=1, output_padding=1),  # 输出: 28x28x1
            nn.Sigmoid() # 将输出值压缩到 [0, 1] 范围
        )

    def encode(self, x):
        h = self.encoder(x)
        mu = self.fc_mu(h)
        logvar = self.fc_logvar(h)
        return mu, logvar

    def reparameterize(self, mu, logvar):
        std = torch.exp(0.5 * logvar)
        eps = torch.randn_like(std)
        return mu + eps * std

    def decode(self, z):
        h = self.decoder_input(z)
        reconstruction = self.decoder(h)
        return reconstruction

    def forward(self, x):
        mu, logvar = self.encode(x)
        z = self.reparameterize(mu, logvar)
        reconstruction = self.decode(z)
        return reconstruction, mu, logvar, z
```

![](img/571a6f32a80cb0c70d0d2b425fa84956_69.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_70.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_71.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_73.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_75.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_76.png)

**核心概念解释：**
*   **编码器 (`encode`)**：将输入图像 `x` 映射为潜在空间的两个向量：均值 `mu` 和方差对数 `logvar`。
*   **重参数化 (`reparameterize`)**：这是VAE的关键。我们从标准正态分布中采样噪声 `epsilon`，然后通过公式 `z = mu + epsilon * exp(0.5 * logvar)` 得到潜在变量 `z`。这使得梯度可以通过 `mu` 和 `logvar` 反向传播。
*   **解码器 (`decode`)**：将潜在变量 `z` 映射回原始图像空间，生成重建图像。

![](img/571a6f32a80cb0c70d0d2b425fa84956_78.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_79.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_81.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_82.png)

---

![](img/571a6f32a80cb0c70d0d2b425fa84956_84.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_86.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_88.png)

## 定义损失函数与训练循环 ⚙️

模型构建完成后，我们需要定义训练过程。VAE的损失函数由两部分组成：重建损失和KL散度。

![](img/571a6f32a80cb0c70d0d2b425fa84956_90.png)

以下是损失函数的计算和训练循环的代码。

![](img/571a6f32a80cb0c70d0d2b425fa84956_92.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_94.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_96.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_98.png)

```python
def loss_function(recon_x, x, mu, logvar):
    # 重建损失 (MSE)
    reconstruction_loss = nn.functional.mse_loss(recon_x, x, reduction='sum')
    # KL散度损失
    kl_divergence = -0.5 * torch.sum(1 + logvar - mu.pow(2) - logvar.exp())
    # 总损失
    total_loss = reconstruction_loss + kl_divergence
    return total_loss, reconstruction_loss, kl_divergence

![](img/571a6f32a80cb0c70d0d2b425fa84956_100.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_102.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_104.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_106.png)

# 初始化模型、优化器
model = ConvVAE(latent_dim=2).to(device)
optimizer = optim.Adam(model.parameters(), lr=learning_rate)

![](img/571a6f32a80cb0c70d0d2b425fa84956_108.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_110.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_112.png)

# 训练循环
for epoch in range(epochs):
    model.train()
    train_loss = 0
    for batch_idx, (data, _) in enumerate(train_loader):
        data = data.to(device)
        optimizer.zero_grad()

        recon_batch, mu, logvar, _ = model(data)
        loss, recon_loss, kl_loss = loss_function(recon_batch, data, mu, logvar)

        loss.backward()
        train_loss += loss.item()
        optimizer.step()

    print(f'Epoch {epoch+1}, Loss: {train_loss / len(train_loader.dataset):.4f}')
```

![](img/571a6f32a80cb0c70d0d2b425fa84956_114.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_116.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_118.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_120.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_122.png)

**损失函数详解：**
总损失公式为：
`总损失 = 重建损失 + KL散度`
其中：
*   **重建损失** 衡量解码器输出与原始输入的差异，这里使用均方误差（MSE）。
*   **KL散度** 促使编码器产生的潜在分布 `q(z|x)` 接近标准正态分布 `p(z)`。其计算公式为：
    `KL = -0.5 * sum(1 + logvar - mu^2 - exp(logvar))`

![](img/571a6f32a80cb0c70d0d2b425fa84956_124.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_126.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_127.png)

---

![](img/571a6f32a80cb0c70d0d2b425fa84956_129.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_130.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_132.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_134.png)

## 结果可视化与采样 🎨

![](img/571a6f32a80cb0c70d0d2b425fa84956_136.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_137.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_139.png)

训练完成后，我们可以查看模型的重建效果、潜在空间分布，并从中采样生成新图像。

![](img/571a6f32a80cb0c70d0d2b425fa84956_141.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_142.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_144.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_146.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_148.png)

以下是进行可视化的代码示例。

![](img/571a6f32a80cb0c70d0d2b425fa84956_150.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_152.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_154.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_155.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_157.png)

```python
import matplotlib.pyplot as plt
import numpy as np

![](img/571a6f32a80cb0c70d0d2b425fa84956_159.png)

# 1. 查看原始图像与重建图像
model.eval()
with torch.no_grad():
    data, _ = next(iter(train_loader))
    data = data[:8].to(device)
    recon, _, _, _ = model(data)

![](img/571a6f32a80cb0c70d0d2b425fa84956_161.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_162.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_164.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_166.png)

# 绘制对比图
fig, axes = plt.subplots(2, 8, figsize=(16, 4))
for i in range(8):
    axes[0, i].imshow(data[i].cpu().squeeze(), cmap='gray')
    axes[0, i].axis('off')
    axes[1, i].imshow(recon[i].cpu().squeeze(), cmap='gray')
    axes[1, i].axis('off')
axes[0, 0].set_ylabel('Original')
axes[1, 0].set_ylabel('Reconstructed')
plt.show()

![](img/571a6f32a80cb0c70d0d2b425fa84956_168.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_169.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_171.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_173.png)

# 2. 可视化潜在空间
def plot_latent_space(model, data_loader, device):
    model.eval()
    latents = []
    labels = []
    with torch.no_grad():
        for data, target in data_loader:
            data = data.to(device)
            mu, logvar = model.encode(data)
            z = model.reparameterize(mu, logvar)
            latents.append(z.cpu())
            labels.append(target)
    latents = torch.cat(latents, dim=0).numpy()
    labels = torch.cat(labels, dim=0).numpy()

    plt.figure(figsize=(8, 6))
    scatter = plt.scatter(latents[:, 0], latents[:, 1], c=labels, cmap='tab10', alpha=0.6, s=2)
    plt.colorbar(scatter)
    plt.xlabel('Latent Dim 1')
    plt.ylabel('Latent Dim 2')
    plt.title('VAE Latent Space')
    plt.show()

![](img/571a6f32a80cb0c70d0d2b425fa84956_175.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_176.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_178.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_180.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_182.png)

plot_latent_space(model, train_loader, device)

![](img/571a6f32a80cb0c70d0d2b425fa84956_184.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_185.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_186.png)

# 3. 从潜在空间采样生成新图像
def sample_from_vae(model, num_samples=10, latent_dim=2):
    model.eval()
    with torch.no_grad():
        # 从标准正态分布采样
        z = torch.randn(num_samples, latent_dim).to(device)
        samples = model.decode(z).cpu()
    return samples

![](img/571a6f32a80cb0c70d0d2b425fa84956_188.png)

samples = sample_from_vae(model, num_samples=10)
# 绘制生成的图像
fig, axes = plt.subplots(1, 10, figsize=(15, 2))
for i in range(10):
    axes[i].imshow(samples[i].squeeze(), cmap='gray')
    axes[i].axis('off')
plt.suptitle('Images Sampled from VAE')
plt.show()
```

![](img/571a6f32a80cb0c70d0d2b425fa84956_190.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_192.png)

**结果分析：**
*   **重建图像**：底部行是模型重建的图像，虽然有些模糊且偶尔会混淆数字（如4和9），但整体上保留了数字的主要特征。
*   **潜在空间**：所有数据点的潜在编码 `z` 大致以原点为中心分布，呈现出类似高斯混合的形态，这符合VAE的训练目标。
*   **图像生成**：通过从标准正态分布中随机采样 `z` 并输入解码器，我们可以生成新的手写数字图像。虽然部分图像质量不高（尤其是当潜在维度仅为2时），但许多生成结果看起来是合理的。

![](img/571a6f32a80cb0c70d0d2b425fa84956_194.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_195.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_197.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_199.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_200.png)

---

![](img/571a6f32a80cb0c70d0d2b425fa84956_202.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_204.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_206.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_207.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_209.png)

## 总结

![](img/571a6f32a80cb0c70d0d2b425fa84956_211.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_213.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_215.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_217.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_219.png)

本节课中我们一起学习了如何在PyTorch中实现一个用于MNIST手写数字的变分自动编码器。

![](img/571a6f32a80cb0c70d0d2b425fa84956_221.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_222.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_224.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_226.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_228.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_229.png)

我们回顾一下核心步骤：
1.  **模型结构**：构建了包含编码器（输出`mu`和`logvar`）、重参数化层和解码器的卷积VAE。
2.  **重参数化技巧**：使用公式 `z = mu + epsilon * exp(0.5 * logvar)` 从分布中采样，使模型可训练。
3.  **损失函数**：定义了结合重建损失（MSE）和KL散度的总损失函数，以同时优化重建能力和潜在空间的正则化。
4.  **训练与评估**：完成了模型的训练循环，并可视化分析了重建效果、潜在空间分布以及采样生成的新图像。

![](img/571a6f32a80cb0c70d0d2b425fa84956_231.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_233.png)

![](img/571a6f32a80cb0c70d0d2b425fa84956_235.png)

由于本例中潜在空间维度设置得很小（仅为2），生成图像的质量和多样性受到限制。在实践中，增大潜在空间的维度通常能获得更清晰、更多样的生成结果。这个简单的VAE为实现更复杂的生成模型（如用于人脸生成）奠定了重要的基础。