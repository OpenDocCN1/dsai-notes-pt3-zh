# 169：L19.6 - 基于 PyTorch 的 DistilBERT 电影评论分类器 🎬

在本节课中，我们将学习如何使用 Hugging Face 的 Transformers 库，基于预训练的 DistilBERT 模型来构建一个电影评论情感分类器。我们将通过代码实践，了解如何加载预训练模型、进行下游任务的微调，并将其性能与我们之前学习的 LSTM 模型进行对比。

---

![](img/154b688314fa0550cc46ed42fc16e4d9_1.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_2.png)

## 📚 概述

![](img/154b688314fa0550cc46ed42fc16e4d9_4.png)

我们之前的长篇讲座涵盖了使用循环神经网络和 Transformer 进行序列建模。我们讨论了带注意力的 RNN、自注意力机制、多头注意力（这些是原始 Transformer 模型中的核心概念），以及一些流行的 Transformer 模型，如 BERT 和 GPT。

BERT 模型更擅长判别式建模任务（如分类预测），而 GPT 则更适用于文本生成。本节课，我们将使用熟悉的电影评论数据集，展示一个简单的 BERT 应用示例，并与我们在第 15 讲中训练的 LSTM 模型性能进行比较。

![](img/154b688314fa0550cc46ed42fc16e4d9_6.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_7.png)

Hugging Face 公司开发了一个被广泛使用的开源 Transformers 库。本节课我们将利用这个库。

![](img/154b688314fa0550cc46ed42fc16e4d9_9.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_10.png)

---

![](img/154b688314fa0550cc46ed42fc16e4d9_12.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_13.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_15.png)

## 🛠️ 环境与数据准备

![](img/154b688314fa0550cc46ed42fc16e4d9_17.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_19.png)

首先，我们需要安装必要的库并准备数据。

![](img/154b688314fa0550cc46ed42fc16e4d9_21.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_22.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_23.png)

以下是需要导入的核心模块：

![](img/154b688314fa0550cc46ed42fc16e4d9_25.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_26.png)

```python
from transformers import DistilBertTokenizer, DistilBertForSequenceClassification
import torch
from torch.utils.data import Dataset, DataLoader
```

![](img/154b688314fa0550cc46ed42fc16e4d9_28.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_29.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_31.png)

我们设置训练轮数为 3，因为模型较大，训练较慢。DistilBERT 是 BERT 的一个精简版，参数量减少 40%，速度提升 60%，同时保留了约 95% 的原始性能。

![](img/154b688314fa0550cc46ed42fc16e4d9_33.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_35.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_36.png)

我们加载预处理好的电影评论 CSV 数据集。该数据集包含评论文本和情感标签（正面/负面），共有 50,000 条评论。

![](img/154b688314fa0550cc46ed42fc16e4d9_37.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_38.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_40.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_41.png)

我们将数据划分为训练集（35,000条）、验证集（5,000条）和测试集（10,000条）。

---

![](img/154b688314fa0550cc46ed42fc16e4d9_43.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_44.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_45.png)

## 🔤 文本编码与数据集构建

![](img/154b688314fa0550cc46ed42fc16e4d9_47.png)

上一节我们准备好了数据，本节中我们来看看如何将文本转换为模型可以处理的格式。

![](img/154b688314fa0550cc46ed42fc16e4d9_49.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_51.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_53.png)

我们使用与预训练模型配套的分词器（Tokenizer）来处理文本。分词器会将文本转换为词汇表对应的 ID，并处理填充（Padding）和截断（Truncation），使所有序列长度统一为 512。

![](img/154b688314fa0550cc46ed42fc16e4d9_54.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_56.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_57.png)

以下是创建编码和构建数据集的步骤：

![](img/154b688314fa0550cc46ed42fc16e4d9_59.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_60.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_61.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_63.png)

```python
# 加载预训练分词器
tokenizer = DistilBertTokenizer.from_pretrained('distilbert-base-uncased')

![](img/154b688314fa0550cc46ed42fc16e4d9_65.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_67.png)

# 对文本进行编码
encodings = tokenizer(list(train_texts), truncation=True, padding=True, max_length=512)

![](img/154b688314fa0550cc46ed42fc16e4d9_68.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_70.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_72.png)

# 构建 PyTorch Dataset
class ReviewDataset(Dataset):
    def __init__(self, encodings, labels):
        self.encodings = encodings
        self.labels = labels
    def __getitem__(self, idx):
        item = {key: torch.tensor(val[idx]) for key, val in self.encodings.items()}
        item['labels'] = torch.tensor(self.labels[idx])
        return item
    def __len__(self):
        return len(self.labels)

train_dataset = ReviewDataset(train_encodings, train_labels)
```

![](img/154b688314fa0550cc46ed42fc16e4d9_74.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_76.png)

然后，我们创建 DataLoader 来批量加载数据。由于模型较大，我们设置较小的批量大小（例如 16）以避免内存问题。

![](img/154b688314fa0550cc46ed42fc16e4d9_77.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_79.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_81.png)

---

![](img/154b688314fa0550cc46ed42fc16e4d9_82.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_84.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_86.png)

## 🤖 加载与配置模型

![](img/154b688314fa0550cc46ed42fc16e4d9_88.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_90.png)

现在，我们来加载预训练的 DistilBERT 模型用于序列分类任务。

![](img/154b688314fa0550cc46ed42fc16e4d9_92.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_94.png)

Transformer 模型的训练通常分为两步：首先在大规模无标签数据上进行预训练，然后在特定下游任务的小规模有标签数据上进行微调。我们直接加载 Hugging Face 提供的预训练模型，并在电影评论数据上进行微调。

![](img/154b688314fa0550cc46ed42fc16e4d9_96.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_98.png)

以下是加载模型和优化器的代码：

![](img/154b688314fa0550cc46ed42fc16e4d9_100.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_101.png)

```python
# 加载预训练模型
model = DistilBertForSequenceClassification.from_pretrained('distilbert-base-uncased', num_labels=2)

![](img/154b688314fa0550cc46ed42fc16e4d9_103.png)

# 使用支持权重衰减的 AdamW 优化器
optimizer = torch.optim.AdamW(model.parameters(), lr=5e-5)

![](img/154b688314fa0550cc46ed42fc16e4d9_105.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_106.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_107.png)

# 使用线性学习率调度器
from transformers import get_linear_schedule_with_warmup
scheduler = get_linear_schedule_with_warmup(optimizer, num_warmup_steps=0, num_training_steps=len(train_dataloader)*epochs)
```

![](img/154b688314fa0550cc46ed42fc16e4d9_109.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_111.png)

我们使用 `DistilBertForSequenceClassification` 来加载模型。优化器选择了 AdamW，它通过解耦权重衰减来实现更好的 L2 正则化。同时，我们采用了线性学习率调度器，这些设置通常能带来更好的性能。

![](img/154b688314fa0550cc46ed42fc16e4d9_113.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_115.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_117.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_119.png)

---

![](img/154b688314fa0550cc46ed42fc16e4d9_121.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_122.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_124.png)

## 🏋️ 模型训练与评估

![](img/154b688314fa0550cc46ed42fc16e4d9_126.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_128.png)

我们将开始训练模型。训练循环与我们之前构建的类似，但需要注意 BERT 模型前向传播的输入和输出格式。

![](img/154b688314fa0550cc46ed42fc16e4d9_130.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_131.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_133.png)

以下是训练循环的核心部分：

![](img/154b688314fa0550cc46ed42fc16e4d9_135.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_137.png)

```python
def train_epoch(model, data_loader, optimizer, scheduler, device):
    model.train()
    total_loss = 0
    for batch in data_loader:
        # 将数据移至设备（如GPU）
        input_ids = batch['input_ids'].to(device)
        attention_mask = batch['attention_mask'].to(device)
        labels = batch['labels'].to(device)

        # 前向传播
        outputs = model(input_ids, attention_mask=attention_mask, labels=labels)
        loss = outputs.loss
        logits = outputs.logits

        # 反向传播
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()
        scheduler.step()

        total_loss += loss.item()
    return total_loss / len(data_loader)
```

![](img/154b688314fa0550cc46ed42fc16e4d9_139.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_141.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_142.png)

模型的前向传播会返回一个元组，包含损失值（loss）和逻辑回归值（logits）。我们直接使用返回的损失进行反向传播。在计算准确率时，我们使用 logits 来获取预测的类别标签。

![](img/154b688314fa0550cc46ed42fc16e4d9_144.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_145.png)

训练过程比 LSTM 慢很多（约20分钟/轮），但最终在测试集上达到了约 92% 的准确率。

![](img/154b688314fa0550cc46ed42fc16e4d9_146.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_147.png)

---

![](img/154b688314fa0550cc46ed42fc16e4d9_149.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_150.png)

## 📊 性能对比与进阶技巧

![](img/154b688314fa0550cc46ed42fc16e4d9_152.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_153.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_155.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_157.png)

我们将 DistilBERT 的性能与之前第15讲中的 LSTM 模型进行对比。

![](img/154b688314fa0550cc46ed42fc16e4d9_159.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_161.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_163.png)

LSTM 模型训练速度极快（每轮不到半分钟），在15轮训练后达到了约 89% 的测试准确率。虽然比 DistilBERT 的 92% 略低，但其效率非常高。

![](img/154b688314fa0550cc46ed42fc16e4d9_165.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_166.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_167.png)

为了进一步提升 DistilBERT 的性能，我们尝试了 Hugging Face 推荐的两个技巧：
1.  使用 AdamW 优化器代替普通 Adam。
2.  使用线性学习率调度器。

![](img/154b688314fa0550cc46ed42fc16e4d9_168.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_170.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_172.png)

这些调整将测试准确率提升到了约 93%。

此外，Hugging Face 的 Transformers 库还提供了一个非常方便的 `Trainer` 类，它封装了训练、评估和多 GPU 支持等功能，可以进一步简化代码并可能带来微小的性能提升。

![](img/154b688314fa0550cc46ed42fc16e4d9_174.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_176.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_177.png)

---

![](img/154b688314fa0550cc46ed42fc16e4d9_178.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_180.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_182.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_183.png)

## 🎯 总结

![](img/154b688314fa0550cc46ed42fc16e4d9_185.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_187.png)

本节课中，我们一起学习了如何使用 Hugging Face 的 Transformers 库来微调预训练的 DistilBERT 模型，完成电影评论情感分类任务。

![](img/154b688314fa0550cc46ed42fc16e4d9_189.png)

我们回顾了关键步骤：
1.  **准备数据**：加载并划分数据集。
2.  **文本编码**：使用预训练分词器将文本转换为模型输入。
3.  **加载模型**：加载 `DistilBertForSequenceClassification` 进行下游任务微调。
4.  **训练与评估**：设置优化器、调度器，编写训练循环，并评估模型性能。
5.  **性能对比**：与高效的 LSTM 模型对比，展示了预训练 Transformer 模型的强大性能。

![](img/154b688314fa0550cc46ed42fc16e4d9_190.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_191.png)

![](img/154b688314fa0550cc46ed42fc16e4d9_193.png)

核心思想是**利用预训练模型在大规模数据上学到的通用语言知识，通过微调使其适应特定的下游任务**。Hugging Face 库提供了丰富的预训练模型和便捷的工具，是探索自然语言处理应用的强大资源。