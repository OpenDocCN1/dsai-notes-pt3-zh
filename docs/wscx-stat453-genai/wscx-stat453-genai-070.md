# P70：L9.5.2 - PyTorch 中的自定义数据加载器（代码示例） 🚀 📚

在本节课中，我们将学习如何在 PyTorch 中创建自定义数据加载器。数据加载器是一个 PyTorch 类，它能让我们比手动操作更方便地批量加载数据。我们将通过两个笔记本示例来演示：一个展示数据加载器本身的基本用法，另一个展示如何在模型训练中使用它。

![](img/363ca9888bed55788c258cb6b3103f4e_1.png)

## 概述与数据准备

我们将使用 MNIST 数据集作为示例。选择 MNIST 的原因是它相对较小，便于上传到 GitHub 供大家快速下载。虽然 PyTorch 的 `torchvision` 库中已有现成的 MNIST 数据集和数据加载器，但这里我们将其视为一个由 PNG 文件和 CSV 文件组成的通用数据集，以演示如何处理自定义数据。

![](img/363ca9888bed55788c258cb6b3103f4e_3.png)

![](img/363ca9888bed55788c258cb6b3103f4e_5.png)

我已经将 MNIST 数据集分成了三个部分：训练集、验证集和测试集。每个部分都存放在独立的文件夹中，包含 PNG 图像文件和一个对应的 CSV 文件。CSV 文件中记录了文件名和对应的类别标签。

![](img/363ca9888bed55788c258cb6b3103f4e_7.png)

以下是数据集的目录结构示例：
```
mnist_train/
    ├── 0.png
    ├── 1.png
    └── ...
mnist_train.csv
```

![](img/363ca9888bed55788c258cb6b3103f4e_9.png)

![](img/363ca9888bed55788c258cb6b3103f4e_11.png)

当然，你也可以选择将所有图像放在一个文件夹中，然后在 CSV 文件中用额外的列来区分训练集、验证集和测试集。具体如何组织取决于你的偏好。

![](img/363ca9888bed55788c258cb6b3103f4e_13.png)

![](img/363ca9888bed55788c258cb6b3103f4e_14.png)

## 第一步：检查数据集

![](img/363ca9888bed55788c258cb6b3103f4e_16.png)

![](img/363ca9888bed55788c258cb6b3103f4e_17.png)

![](img/363ca9888bed55788c258cb6b3103f4e_18.png)

![](img/363ca9888bed55788c258cb6b3103f4e_20.png)

![](img/363ca9888bed55788c258cb6b3103f4e_22.png)

![](img/363ca9888bed55788c258cb6b3103f4e_24.png)

![](img/363ca9888bed55788c258cb6b3103f4e_25.png)

在开始构建数据加载器之前，通常需要先检查数据集。我们可以使用 Python 的 `PIL`（Pillow）库来打开和查看图像。

![](img/363ca9888bed55788c258cb6b3103f4e_27.png)

![](img/363ca9888bed55788c258cb6b3103f4e_29.png)

![](img/363ca9888bed55788c258cb6b3103f4e_30.png)

```python
from PIL import Image
import matplotlib.pyplot as plt

![](img/363ca9888bed55788c258cb6b3103f4e_32.png)

![](img/363ca9888bed55788c258cb6b3103f4e_33.png)

![](img/363ca9888bed55788c258cb6b3103f4e_35.png)

# 打开一张图像
img = Image.open('mnist_train/0.png')
print(f'图像尺寸: {img.size}')  # 输出: (28, 28)
print(f'图像模式: {img.mode}')  # 输出: L (灰度图)

![](img/363ca9888bed55788c258cb6b3103f4e_37.png)

![](img/363ca9888bed55788c258cb6b3103f4e_38.png)

# 显示图像
plt.imshow(img, cmap='binary')
plt.show()
```

![](img/363ca9888bed55788c258cb6b3103f4e_40.png)

通过检查，我们了解到图像是 28x28 像素的灰度图，像素值范围在 0 到 255 之间。

接下来，我们使用 `pandas` 库来查看 CSV 文件的内容。

![](img/363ca9888bed55788c258cb6b3103f4e_42.png)

```python
import pandas as pd

![](img/363ca9888bed55788c258cb6b3103f4e_44.png)

![](img/363ca9888bed55788c258cb6b3103f4e_45.png)

![](img/363ca9888bed55788c258cb6b3103f4e_47.png)

![](img/363ca9888bed55788c258cb6b3103f4e_49.png)

# 加载 CSV 文件
df_train = pd.read_csv('mnist_train.csv')
print(df_train.head())
```

CSV 文件包含 `filename` 和 `label` 两列。为了演示方便，我特意将每个子集的数据量缩小到了 256 张图像。

![](img/363ca9888bed55788c258cb6b3103f4e_51.png)

![](img/363ca9888bed55788c258cb6b3103f4e_53.png)

![](img/363ca9888bed55788c258cb6b3103f4e_55.png)

![](img/363ca9888bed55788c258cb6b3103f4e_57.png)

## 第二步：创建自定义 Dataset 类

![](img/363ca9888bed55788c258cb6b3103f4e_59.png)

![](img/363ca9888bed55788c258cb6b3103f4e_61.png)

![](img/363ca9888bed55788c258cb6b3103f4e_63.png)

PyTorch 的数据加载需要两个核心部分：`Dataset` 和 `DataLoader`。`Dataset` 类负责定义如何读取单个数据样本，而 `DataLoader` 则负责批量加载和打乱数据。

![](img/363ca9888bed55788c258cb6b3103f4e_65.png)

![](img/363ca9888bed55788c258cb6b3103f4e_67.png)

![](img/363ca9888bed55788c258cb6b3103f4e_69.png)

我们需要继承 PyTorch 的 `torch.utils.data.Dataset` 类来创建自己的数据集类。

![](img/363ca9888bed55788c258cb6b3103f4e_71.png)

![](img/363ca9888bed55788c258cb6b3103f4e_73.png)

```python
import torch
from torch.utils.data import Dataset
from PIL import Image

![](img/363ca9888bed55788c258cb6b3103f4e_75.png)

![](img/363ca9888bed55788c258cb6b3103f4e_77.png)

![](img/363ca9888bed55788c258cb6b3103f4e_79.png)

![](img/363ca9888bed55788c258cb6b3103f4e_80.png)

![](img/363ca9888bed55788c258cb6b3103f4e_82.png)

![](img/363ca9888bed55788c258cb6b3103f4e_84.png)

class MyDataset(Dataset):
    def __init__(self, csv_path, img_dir, transform=None):
        """
        初始化函数。
        csv_path: CSV 文件路径。
        img_dir: 图像文件夹路径。
        transform: 可选的图像变换函数。
        """
        self.df = pd.read_csv(csv_path)
        self.img_dir = img_dir
        self.transform = transform
        # 保存图像文件名和标签
        self.img_names = self.df['filename'].values
        self.y = self.df['label'].values

    def __len__(self):
        """返回数据集的大小。"""
        return self.y.shape[0]

    def __getitem__(self, index):
        """根据索引加载并返回一个数据样本（图像和标签）。"""
        # 构建图像完整路径
        img_path = os.path.join(self.img_dir, self.img_names[index])
        # 打开图像
        image = Image.open(img_path)
        # 应用变换（如果有）
        if self.transform is not None:
            image = self.transform(image)
        # 获取对应标签
        label = self.y[index]
        return image, label
```

![](img/363ca9888bed55788c258cb6b3103f4e_86.png)

![](img/363ca9888bed55788c258cb6b3103f4e_87.png)

![](img/363ca9888bed55788c258cb6b3103f4e_89.png)

![](img/363ca9888bed55788c258cb6b3103f4e_91.png)

在上面的代码中：
*   `__init__` 方法用于初始化，读取 CSV 文件并保存必要的信息。
*   `__len__` 方法返回数据集的样本总数，这对于 DataLoader 确定何时完成一个 epoch 至关重要。
*   `__getitem__` 方法是核心，它根据给定的索引 `index` 加载对应的图像和标签。`DataLoader` 会随机生成索引序列来调用此方法，从而实现数据的随机打乱。

![](img/363ca9888bed55788c258cb6b3103f4e_92.png)

![](img/363ca9888bed55788c258cb6b3103f4e_94.png)

![](img/363ca9888bed55788c258cb6b3103f4e_96.png)

![](img/363ca9888bed55788c258cb6b3103f4e_97.png)

## 第三步：设置数据变换与创建 DataLoader

![](img/363ca9888bed55788c258cb6b3103f4e_98.png)

![](img/363ca9888bed55788c258cb6b3103f4e_100.png)

创建好 `Dataset` 后，我们就可以用它来实例化 `DataLoader`。在将图像输入神经网络之前，通常需要进行一些预处理，例如转换为张量（Tensor）和归一化。我们可以使用 `torchvision.transforms` 来定义这些变换。

```python
from torchvision import transforms

![](img/363ca9888bed55788c258cb6b3103f4e_102.png)

![](img/363ca9888bed55788c258cb6b3103f4e_104.png)

# 定义一个简单的变换：将图像转换为张量（同时自动除以255进行归一化）
transform = transforms.Compose([
    transforms.ToTensor()
])

![](img/363ca9888bed55788c258cb6b3103f4e_105.png)

![](img/363ca9888bed55788c258cb6b3103f4e_106.png)

# 创建训练、验证和测试数据集实例
train_dataset = MyDataset(csv_path='mnist_train.csv',
                          img_dir='mnist_train',
                          transform=transform)

val_dataset = MyDataset(csv_path='mnist_valid.csv',
                        img_dir='mnist_valid',
                        transform=transform)

test_dataset = MyDataset(csv_path='mnist_test.csv',
                         img_dir='mnist_test',
                         transform=transform)
```

现在，我们可以使用这些数据集来创建 `DataLoader`。

```python
from torch.utils.data import DataLoader

![](img/363ca9888bed55788c258cb6b3103f4e_108.png)

BATCH_SIZE = 32

train_loader = DataLoader(dataset=train_dataset,
                          batch_size=BATCH_SIZE,
                          shuffle=True,
                          num_workers=0,  # 对于MNIST这样的小数据集，设为0以避免潜在问题
                          drop_last=True)

![](img/363ca9888bed55788c258cb6b3103f4e_110.png)

![](img/363ca9888bed55788c258cb6b3103f4e_111.png)

![](img/363ca9888bed55788c258cb6b3103f4e_112.png)

![](img/363ca9888bed55788c258cb6b3103f4e_114.png)

val_loader = DataLoader(dataset=val_dataset,
                        batch_size=BATCH_SIZE,
                        shuffle=False,
                        num_workers=0)

![](img/363ca9888bed55788c258cb6b3103f4e_116.png)

![](img/363ca9888bed55788c258cb6b3103f4e_118.png)

![](img/363ca9888bed55788c258cb6b3103f4e_120.png)

![](img/363ca9888bed55788c258cb6b3103f4e_122.png)

test_loader = DataLoader(dataset=test_dataset,
                         batch_size=BATCH_SIZE,
                         shuffle=False,
                         num_workers=0)
```

![](img/363ca9888bed55788c258cb6b3103f4e_124.png)

![](img/363ca9888bed55788c258cb6b3103f4e_126.png)

![](img/363ca9888bed55788c258cb6b3103f4e_128.png)

![](img/363ca9888bed55788c258cb6b3103f4e_130.png)

![](img/363ca9888bed55788c258cb6b3103f4e_132.png)

以下是 `DataLoader` 关键参数的解释：
*   `batch_size`: 每个小批量（mini-batch）包含的样本数。
*   `shuffle`: 是否在每个 epoch 开始时打乱数据顺序（通常训练集设为 `True`，验证和测试集设为 `False`）。
*   `num_workers`: 用于数据加载的子进程数量。大于 0 时可以利用多 CPU 核心并行预加载下一个批次的数据，提高 GPU 利用率。但对于 MNIST 这类极小的数据集，有时设为 0 可以避免“打开文件过多”的错误。
*   `drop_last`: 当数据集样本数不能被 `batch_size` 整除时，是否丢弃最后一个不完整的小批量。有时丢弃它可以避免最后一个小批量噪声过大影响训练。

![](img/363ca9888bed55788c258cb6b3103f4e_134.png)

![](img/363ca9888bed55788c258cb6b3103f4e_135.png)

![](img/363ca9888bed55788c258cb6b3103f4e_137.png)

![](img/363ca9888bed55788c258cb6b3103f4e_139.png)

我们可以测试一下 `DataLoader` 是否工作正常。

![](img/363ca9888bed55788c258cb6b3103f4e_141.png)

![](img/363ca9888bed55788c258cb6b3103f4e_142.png)

![](img/363ca9888bed55788c258cb6b3103f4e_144.png)

![](img/363ca9888bed55788c258cb6b3103f4e_146.png)

```python
# 模拟一个训练循环
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
for epoch in range(2):
    for batch_idx, (features, targets) in enumerate(train_loader):
        features = features.to(device)
        targets = targets.to(device)
        # 这里应该是你的模型前向传播、计算损失和反向传播的代码
        print(f'Epoch: {epoch+1:03d} | Batch: {batch_idx:03d} | Features Shape: {features.shape}')
        # 只打印前几个批次
        if batch_idx > 2:
            break
```

![](img/363ca9888bed55788c258cb6b3103f4e_148.png)

![](img/363ca9888bed55788c258cb6b3103f4e_150.png)

![](img/363ca9888bed55788c258cb6b3103f4e_152.png)

输出一个批次的形状：
```python
features, targets = next(iter(train_loader))
print(f'一个批次的图像形状: {features.shape}')  # 输出: torch.Size([32, 1, 28, 28])
print(f'一个批次的标签形状: {targets.shape}')    # 输出: torch.Size([32])
```
形状 `[32, 1, 28, 28]` 表示：批量大小 32，1个颜色通道（灰度），图像高 28 像素，宽 28 像素。

![](img/363ca9888bed55788c258cb6b3103f4e_154.png)

![](img/363ca9888bed55788c258cb6b3103f4e_156.png)

![](img/363ca9888bed55788c258cb6b3103f4e_158.png)

## 第四步：在模型训练中使用自定义 DataLoader

上一节我们创建了可用的数据加载器，本节我们来看看如何将其整合到一个完整的模型训练流程中。为了保持代码整洁和可复用，我将一些通用功能（如训练循环、准确率计算、绘图）写在了单独的辅助脚本中。

![](img/363ca9888bed55788c258cb6b3103f4e_160.png)

![](img/363ca9888bed55788c258cb6b3103f4e_162.png)

首先，我们定义一个简单的多层感知机（MLP）模型。注意，我们使用了 `nn.Flatten()` 层，它可以自动将输入的 `[batch, 1, 28, 28]` 形状展平为 `[batch, 784]`，省去了手动重塑的步骤。

![](img/363ca9888bed55788c258cb6b3103f4e_164.png)

![](img/363ca9888bed55788c258cb6b3103f4e_165.png)

![](img/363ca9888bed55788c258cb6b3103f4e_167.png)

![](img/363ca9888bed55788c258cb6b3103f4e_169.png)

![](img/363ca9888bed55788c258cb6b3103f4e_171.png)

```python
import torch.nn as nn

![](img/363ca9888bed55788c258cb6b3103f4e_173.png)

![](img/363ca9888bed55788c258cb6b3103f4e_175.png)

class MultilayerPerceptron(nn.Module):
    def __init__(self, num_features, num_hidden, num_classes):
        super().__init__()
        self.model = nn.Sequential(
            nn.Flatten(), # 将 [batch, 1, 28, 28] 展平为 [batch, 784]
            nn.Linear(num_features, num_hidden),
            nn.Sigmoid(),
            nn.Linear(num_hidden, num_classes)
            # 注意：这里没有 Softmax，因为 CrossEntropyLoss 内部会处理
        )

    def forward(self, x):
        logits = self.model(x)
        return logits
```

![](img/363ca9888bed55788c258cb6b3103f4e_177.png)

![](img/363ca9888bed55788c258cb6b3103f4e_178.png)

![](img/363ca9888bed55788c258cb6b3103f4e_180.png)

![](img/363ca9888bed55788c258cb6b3103f4e_182.png)

接下来是训练设置和训练循环。我们使用之前创建的 `train_loader`, `val_loader` 和 `test_loader`。

![](img/363ca9888bed55788c258cb6b3103f4e_184.png)

![](img/363ca9888bed55788c258cb6b3103f4e_185.png)

```python
import torch.optim as optim
from helper_train import train_model # 假设训练循环封装在 helper_train.py 中
from helper_evaluate import compute_accuracy # 假设准确率计算封装在 helper_evaluate.py 中

![](img/363ca9888bed55788c258cb6b3103f4e_187.png)

# 超参数设置
RANDOM_SEED = 123
BATCH_SIZE = 32
NUM_EPOCHS = 10
LEARNING_RATE = 0.1

![](img/363ca9888bed55788c258cb6b3103f4e_189.png)

![](img/363ca9888bed55788c258cb6b3103f4e_191.png)

![](img/363ca9888bed55788c258cb6b3103f4e_193.png)

# 设置随机种子以保证结果可复现
torch.manual_seed(RANDOM_SEED)

![](img/363ca9888bed55788c258cb6b3103f4e_195.png)

# 初始化模型、损失函数和优化器
model = MultilayerPerceptron(num_features=28*28, num_hidden=100, num_classes=10)
model = model.to(device)
optimizer = optim.SGD(model.parameters(), lr=LEARNING_RATE)
criterion = nn.CrossEntropyLoss()

![](img/363ca9888bed55788c258cb6b3103f4e_197.png)

![](img/363ca9888bed55788c258cb6b3103f4e_198.png)

![](img/363ca9888bed55788c258cb6b3103f4e_200.png)

![](img/363ca9888bed55788c258cb6b3103f4e_202.png)

# 开始训练
train_losses, val_losses, train_accs, val_accs = train_model(
    model=model,
    num_epochs=NUM_EPOCHS,
    train_loader=train_loader,
    val_loader=val_loader,
    test_loader=test_loader,
    optimizer=optimizer,
    criterion=criterion,
    device=device
)
```

![](img/363ca9888bed55788c258cb6b3103f4e_204.png)

![](img/363ca9888bed55788c258cb6b3103f4e_206.png)

训练完成后，我们可以绘制损失和准确率曲线来观察训练过程。

![](img/363ca9888bed55788c258cb6b3103f4e_208.png)

![](img/363ca9888bed55788c258cb6b3103f4e_209.png)

![](img/363ca9888bed55788c258cb6b3103f4e_210.png)

![](img/363ca9888bed55788c258cb6b3103f4e_212.png)

![](img/363ca9888bed55788c258cb6b3103f4e_214.png)

```python
from helper_plotting import plot_training_loss, plot_accuracy

![](img/363ca9888bed55788c258cb6b3103f4e_216.png)

![](img/363ca9888bed55788c258cb6b3103f4e_217.png)

![](img/363ca9888bed55788c258cb6b3103f4e_219.png)

![](img/363ca9888bed55788c258cb6b3103f4e_221.png)

plot_training_loss(train_losses, val_losses)
plot_accuracy(train_accs, val_accs)
```

![](img/363ca9888bed55788c258cb6b3103f4e_223.png)

![](img/363ca9888bed55788c258cb6b3103f4e_225.png)

最后，我们可以展示一些测试样本的预测结果，直观地查看模型的性能。

![](img/363ca9888bed55788c258cb6b3103f4e_227.png)

![](img/363ca9888bed55788c258cb6b3103f4e_229.png)

```python
from helper_plotting import show_examples

![](img/363ca9888bed55788c258cb6b3103f4e_231.png)

![](img/363ca9888bed55788c258cb6b3103f4e_232.png)

![](img/363ca9888bed55788c258cb6b3103f4e_233.png)

![](img/363ca9888bed55788c258cb6b3103f4e_235.png)

show_examples(model, test_loader, device)
```
该函数会显示一批测试图像，并在每张图下方标注模型的预测结果（P）和真实标签（T）。

![](img/363ca9888bed55788c258cb6b3103f4e_237.png)

![](img/363ca9888bed55788c258cb6b3103f4e_238.png)

![](img/363ca9888bed55788c258cb6b3103f4e_240.png)

![](img/363ca9888bed55788c258cb6b3103f4e_242.png)

## 总结

![](img/363ca9888bed55788c258cb6b3103f4e_244.png)

![](img/363ca9888bed55788c258cb6b3103f4e_246.png)

![](img/363ca9888bed55788c258cb6b3103f4e_248.png)

本节课我们一起学习了 PyTorch 中自定义数据加载器的完整流程。

![](img/363ca9888bed55788c258cb6b3103f4e_250.png)

![](img/363ca9888bed55788c258cb6b3103f4e_252.png)

![](img/363ca9888bed55788c258cb6b3103f4e_254.png)

![](img/363ca9888bed55788c258cb6b3103f4e_255.png)

![](img/363ca9888bed55788c258cb6b3103f4e_256.png)

我们首先了解了如何通过继承 `torch.utils.data.Dataset` 类来创建自定义数据集，核心是实现 `__len__` 和 `__getitem__` 方法。接着，我们使用 `torch.utils.data.DataLoader` 将数据集包装起来，以便进行批量加载、打乱和多进程预读取。我们还探讨了 `torchvision.transforms` 在图像预处理中的应用。

![](img/363ca9888bed55788c258cb6b3103f4e_258.png)

![](img/363ca9888bed55788c258cb6b3103f4e_260.png)

![](img/363ca9888bed55788c258cb6b3103f4e_261.png)

![](img/363ca9888bed55788c258cb6b3103f4e_263.png)

最后，我们将自定义的数据加载器整合到了一个完整的模型训练流程中，包括模型定义、训练循环、评估和可视化。通过将通用代码模块化到辅助脚本中，我们使得主训练代码更加清晰和易于维护。

![](img/363ca9888bed55788c258cb6b3103f4e_265.png)

![](img/363ca9888bed55788c258cb6b3103f4e_267.png)

掌握自定义数据加载器是处理真实世界、非标准数据集的关键一步，它为你使用 PyTorch 进行各种深度学习项目打下了坚实的基础。