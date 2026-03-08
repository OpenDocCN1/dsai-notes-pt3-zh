# 136：L16.4 - PyTorch 中的卷积自动编码器 🧠

![](img/f7a8252ead9e202d89946be554f92300_1.png)

在本节课中，我们将学习如何在 PyTorch 中实现一个卷积自动编码器。我们将从导入必要的库开始，逐步构建模型，并最终训练它来重建手写数字图像。通过这个过程，你将理解自动编码器的核心组件：编码器和解码器，以及它们如何协同工作来学习数据的压缩表示。

![](img/f7a8252ead9e202d89946be554f92300_2.png)

![](img/f7a8252ead9e202d89946be554f92300_3.png)

---

![](img/f7a8252ead9e202d89946be554f92300_5.png)

## 环境准备与数据加载

首先，我们需要导入必要的库并设置环境。我们将使用 PyTorch 来构建和训练模型，并使用 Matplotlib 来可视化结果。

```python
import torch
import torch.nn as nn
import torch.optim as optim
from torchvision import datasets, transforms
import matplotlib.pyplot as plt
```

接下来，我们定义数据加载器。与分类任务不同，自动编码器通常只使用训练集，因为我们关注的是输入与重建输出之间的差异，而不是分类精度。

![](img/f7a8252ead9e202d89946be554f92300_7.png)

![](img/f7a8252ead9e202d89946be554f92300_9.png)

![](img/f7a8252ead9e202d89946be554f92300_11.png)

```python
# 定义数据转换
transform = transforms.Compose([
    transforms.ToTensor(),
])

# 加载 MNIST 训练集
train_dataset = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
train_loader = torch.utils.data.DataLoader(train_dataset, batch_size=32, shuffle=True)
```

---

## 构建卷积自动编码器模型

![](img/f7a8252ead9e202d89946be554f92300_13.png)

上一节我们介绍了数据准备，本节中我们来看看如何构建模型。我们将模型分为编码器和解码器两个独立的 `Sequential` 模块，这有助于后续将它们作为特征提取器和图像生成器单独使用。

![](img/f7a8252ead9e202d89946be554f92300_15.png)

![](img/f7a8252ead9e202d89946be554f92300_17.png)

以下是模型的核心结构定义：

```python
class ConvAutoencoder(nn.Module):
    def __init__(self):
        super(ConvAutoencoder, self).__init__()
        
        # 编码器
        self.encoder = nn.Sequential(
            nn.Conv2d(1, 32, kernel_size=3, padding=1),  # 输出: (32, 28, 28)
            nn.ReLU(),
            nn.Conv2d(32, 64, kernel_size=3, stride=2, padding=1), # 输出: (64, 14, 14)
            nn.ReLU(),
            nn.Conv2d(64, 64, kernel_size=3, padding=1), # 输出: (64, 14, 14)
            nn.ReLU(),
            nn.Conv2d(64, 64, kernel_size=3, padding=1), # 输出: (64, 14, 14)
            nn.ReLU(),
            nn.Flatten(), # 输出: 64*14*14 = 12544
            nn.Linear(12544, 2) # 压缩为2维潜在空间
        )
        
        # 解码器
        self.decoder = nn.Sequential(
            nn.Linear(2, 12544),
            nn.Unflatten(1, (64, 14, 14)), # 重塑为 (64, 14, 14)
            nn.ConvTranspose2d(64, 64, kernel_size=3, padding=1),
            nn.ReLU(),
            nn.ConvTranspose2d(64, 64, kernel_size=3, padding=1),
            nn.ReLU(),
            nn.ConvTranspose2d(64, 32, kernel_size=3, stride=2, padding=1, output_padding=1), # 输出: (32, 28, 28)
            nn.ReLU(),
            nn.ConvTranspose2d(32, 1, kernel_size=3, padding=1), # 输出: (1, 28, 28)
            nn.Sigmoid() # 将像素值压缩到 [0, 1] 范围
        )
    
    def forward(self, x):
        encoded = self.encoder(x)
        decoded = self.decoder(encoded)
        return decoded
```

![](img/f7a8252ead9e202d89946be554f92300_19.png)

![](img/f7a8252ead9e202d89946be554f92300_21.png)

![](img/f7a8252ead9e202d89946be554f92300_23.png)

**核心概念解释**：
*   **编码器**：通过一系列卷积层逐步减少空间尺寸并增加通道数，最后通过一个全连接层将数据压缩到一个低维的**潜在空间向量**（本例中为2维）。公式可以表示为：`z = encoder(x)`。
*   **解码器**：接收潜在空间向量 `z`，通过全连接层和转置卷积层逐步恢复图像的空间尺寸和通道数，最终输出与输入同尺寸的重建图像。公式为：`x_reconstructed = decoder(z)`。
*   **Sigmoid 激活函数**：确保输出像素值在 [0, 1] 范围内，与归一化的输入图像相匹配。

---

## 训练模型

![](img/f7a8252ead9e202d89946be554f92300_25.png)

![](img/f7a8252ead9e202d89946be554f92300_27.png)

模型构建完成后，我们需要定义训练循环。自动编码器的训练目标是最小化重建图像与原始图像之间的差异。

![](img/f7a8252ead9e202d89946be554f92300_29.png)

![](img/f7a8252ead9e202d89946be554f92300_31.png)

以下是训练过程的关键步骤：

![](img/f7a8252ead9e202d89946be554f92300_33.png)

![](img/f7a8252ead9e202d89946be554f92300_35.png)

1.  **定义损失函数和优化器**：我们使用均方误差损失来衡量重建误差，并使用 Adam 优化器。
    ```python
    model = ConvAutoencoder()
    criterion = nn.MSELoss()
    optimizer = optim.Adam(model.parameters())
    ```

![](img/f7a8252ead9e202d89946be554f92300_37.png)

2.  **训练循环**：在每个批次中，我们将图像输入编码器，获取重建图像，计算损失，并反向传播更新权重。
    ```python
    def train_autoencoder(model, train_loader, criterion, optimizer, num_epochs):
        model.train()
        for epoch in range(num_epochs):
            running_loss = 0.0
            for data in train_loader:
                img, _ = data # 自动编码器不使用标签
                optimizer.zero_grad()
                
                # 前向传播
                output = model(img)
                loss = criterion(output, img) # 比较输出与输入
                
                # 反向传播和优化
                loss.backward()
                optimizer.step()
                
                running_loss += loss.item()
            print(f'Epoch [{epoch+1}/{num_epochs}], Loss: {running_loss/len(train_loader):.4f}')
    ```

![](img/f7a8252ead9e202d89946be554f92300_39.png)

![](img/f7a8252ead9e202d89946be554f92300_40.png)

3.  **开始训练**：我们运行训练循环20个周期。
    ```python
    train_autoencoder(model, train_loader, criterion, optimizer, num_epochs=20)
    ```

![](img/f7a8252ead9e202d89946be554f92300_42.png)

---

![](img/f7a8252ead9e202d89946be554f92300_44.png)

![](img/f7a8252ead9e202d89946be554f92300_45.png)

## 结果分析与可视化

训练完成后，我们可以评估模型的表现。由于我们使用了极端的2维潜在空间，重建图像会显得比较模糊，但依然能辨认出数字轮廓。

以下是几种可视化方法：

![](img/f7a8252ead9e202d89946be554f92300_47.png)

![](img/f7a8252ead9e202d89946be554f92300_49.png)

![](img/f7a8252ead9e202d89946be554f92300_51.png)

1.  **比较原始图像与重建图像**：
    ```python
    # 获取一个批次的测试图像
    dataiter = iter(train_loader)
    images, _ = next(dataiter)
    with torch.no_grad():
        reconstructed = model(images)
    
    # 绘制对比图
    fig, axes = plt.subplots(2, 8, figsize=(12, 4))
    for i in range(8):
        axes[0, i].imshow(images[i].squeeze(), cmap='gray')
        axes[0, i].axis('off')
        axes[1, i].imshow(reconstructed[i].squeeze(), cmap='gray')
        axes[1, i].axis('off')
    plt.show()
    ```
    结果显示，顶部为原始图像，底部为重建图像。重建图像较为模糊，例如数字“4”可能被误重建为“9”，这是因为它们在2维潜在空间中的表示区域有重叠。

![](img/f7a8252ead9e202d89946be554f92300_53.png)

2.  **可视化潜在空间**：我们可以将训练集中所有图像的2维编码绘制出来，并用颜色区分数字类别。
    ```python
    def plot_latent_space(model, data_loader):
        model.eval()
        latent_vectors = []
        labels = []
        with torch.no_grad():
            for img, label in data_loader:
                latent = model.encoder(img)
                latent_vectors.append(latent)
                labels.append(label)
        latent_vectors = torch.cat(latent_vectors, dim=0).numpy()
        labels = torch.cat(labels, dim=0).numpy()
        
        plt.figure(figsize=(8,6))
        scatter = plt.scatter(latent_vectors[:, 0], latent_vectors[:, 1], c=labels, cmap='tab10', alpha=0.6)
        plt.colorbar(scatter)
        plt.xlabel('Latent Dimension 1')
        plt.ylabel('Latent Dimension 2')
        plt.title('2D Latent Space Visualization')
        plt.show()
    
    plot_latent_space(model, train_loader)
    ```
    从图中可以看到，相似的数字（如所有的“0”和“1”）在潜在空间中会聚集在一起，但不同类别之间也存在大量重叠区域，这解释了为什么重建会出现混淆。

![](img/f7a8252ead9e202d89946be554f92300_55.png)

3.  **使用解码器生成新图像**：我们可以从潜在空间中任意选取一个点，通过解码器生成对应的图像。
    ```python
    def generate_from_latent(model, latent_point):
        model.eval()
        with torch.no_grad():
            # latent_point 是一个形状为 (1, 2) 的张量
            generated = model.decoder(latent_point)
            return generated.squeeze()
    
    # 例如，从潜在空间中心附近采样
    sample_point = torch.tensor([[-2.5, 2.5]])
    generated_img = generate_from_latent(model, sample_point)
    plt.imshow(generated_img, cmap='gray')
    plt.axis('off')
    plt.show()
    ```
    如果采样点位于训练数据分布之外，生成的图像可能是不合理的“幻想”数字。这引出了对更高级生成模型（如变分自动编码器）的需求。

---

## 总结

本节课中我们一起学习了如何在 PyTorch 中实现一个卷积自动编码器。我们首先构建了将图像压缩到2维潜在空间的编码器，以及从该空间重建图像的解码器。接着，我们使用均方误差损失训练模型，以最小化重建误差。最后，我们通过可视化重建结果、潜在空间分布以及图像生成，深入理解了自动编码器的工作原理和局限性。

![](img/f7a8252ead9e202d89946be554f92300_57.png)

![](img/f7a8252ead9e202d89946be554f92300_58.png)

![](img/f7a8252ead9e202d89946be554f92300_59.png)

![](img/f7a8252ead9e202d89946be554f92300_60.png)

![](img/f7a8252ead9e202d89946be554f92300_62.png)

关键要点包括：
*   自动编码器由**编码器**和**解码器**组成，用于学习数据的有效表示。
*   使用**均方误差损失**来优化重建质量。
*   极低维的潜在空间会导致信息丢失和模糊的重建结果。
*   潜在空间的可视化揭示了数据点之间的相似性关系。
*   基本的自动编码器在从任意点生成逼真新数据方面能力有限，这为学习更强大的生成模型（如变分自动编码器）奠定了基础。