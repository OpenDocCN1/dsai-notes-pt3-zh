# 131：L15.7 - PyTorch 中的 RNN 情感分类器 🎬









在本节课中，我们将学习如何在 PyTorch 中实现一个用于情感分类的循环神经网络。我们将使用一个“多对一”的 RNN 架构，将一段文本（如电影评论）作为输入，并输出一个类别标签（如正面或负面情感）。我们将从数据准备、模型构建到训练和预测，完整地走一遍流程。



---





## 1. 概述与准备工作 📋




上一节我们介绍了“多对一”RNN的基本概念。本节中，我们来看看如何用 PyTorch 和 TorchText 库具体实现一个情感分类器。





首先，我们需要设置一些通用参数并导入必要的库。



以下是核心参数设置：
```python
VOCAB_SIZE = 20000
LEARNING_RATE = 0.001
BATCH_SIZE = 64
NUM_EPOCHS = 10
EMBEDDING_DIM = 128
HIDDEN_DIM = 256
NUM_CLASSES = 2
```






我们将使用 IMDB 电影评论数据集。为了简化预处理步骤，我们从指定链接下载一个已处理好的版本。





```python
import pandas as pd
import torch
import torchtext
from torchtext.legacy import data
import spacy
# 下载并加载数据集
df = pd.read_csv('imdb_dataset.csv')
# 为保持代码一致性，重命名列
TEXT_COLUMN_NAME = 'review'
LABEL_COLUMN_NAME = 'sentiment'
df = df.rename(columns={df.columns[0]: TEXT_COLUMN_NAME, df.columns[1]: LABEL_COLUMN_NAME})
```





---






## 2. 使用 TorchText 处理数据 🔧




现在，我们需要将原始文本数据转换为模型可以处理的格式。我们将使用 SpaCy 进行分词，并使用 TorchText 的 `legacy` API 来构建数据管道。




首先，定义用于处理文本和标签的 `Field`。











```python
# 加载 SpaCy 英语分词器
spacy_en = spacy.load('en_core_web_sm')
def tokenizer(text):
    return [tok.text for tok in spacy_en.tokenizer(text)]
# 定义字段
TEXT = data.Field(tokenize=tokenizer, lower=True, include_lengths=False)
LABEL = data.LabelField(dtype=torch.long)
```




接下来，使用 `TabularDataset` 加载我们的 CSV 文件，并按照指定字段进行解析。



```python
fields = [(TEXT_COLUMN_NAME, TEXT), (LABEL_COLUMN_NAME, LABEL)]
dataset = data.TabularDataset(
    path='imdb_dataset.csv',
    format='csv',
    fields=fields,
    skip_header=True
)
```


然后，我们将数据集分割为训练集、验证集和测试集。






```python
# 首先分割出测试集
train_data, test_data = dataset.split(split_ratio=0.8)
# 再从训练集中分割出验证集
train_data, valid_data = train_data.split(split_ratio=0.85)
print(f'训练集: {len(train_data)}')
print(f'验证集: {len(valid_data)}')
print(f'测试集: {len(test_data)}')
```




---





## 3. 构建词汇表 📚



词汇表将每个单词映射到一个唯一的整数索引。我们只在训练集上构建词汇表，以防止信息从验证集和测试集泄露。






以下是构建词汇表的步骤：




```python
# 基于训练集构建词汇表，并限制最常出现的20000个词
TEXT.build_vocab(train_data, max_size=VOCAB_SIZE)
LABEL.build_vocab(train_data)
print(f"词汇表大小: {len(TEXT.vocab)}")
print(f"类别: {LABEL.vocab.stoi}")
```
词汇表大小会是 `VOCAB_SIZE + 2`，因为包含了 `<unk>`（未知词）和 `<pad>`（填充）两个特殊标记。




---



## 4. 创建数据加载器 ⚙️




为了高效训练，我们使用 TorchText 的 `BucketIterator`。它会将长度相近的句子分到同一个批次中，从而减少所需的填充（padding）量，提升计算效率。















```python
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
train_loader, valid_loader, test_loader = data.BucketIterator.splits(
    (train_data, valid_data, test_data),
    batch_size=BATCH_SIZE,
    sort_within_batch=True,
    sort_key=lambda x: len(x.text),
    device=device
)
```




让我们检查一下第一个批次的数据形状，确保一切正常。
```python
for batch in train_loader:
    text, labels = batch.review, batch.sentiment
    print(f'文本张量形状: {text.shape}') # (句子长度, 批次大小)
    print(f'标签张量形状: {labels.shape}') # (批次大小,)
    break
```
注意，RNN 输入的张量形状通常是 `(序列长度, 批次大小)`，这与卷积网络不同。






---


## 5. 构建 LSTM 模型 🧠






我们的模型将包含三个主要部分：嵌入层（Embedding Layer）、LSTM 层和全连接输出层。







以下是模型的定义：










```python
import torch.nn as nn
class RNNClassifier(nn.Module):
    def __init__(self, vocab_size, embed_dim, hidden_dim, output_dim):
        super().__init__()
        self.embedding = nn.Embedding(vocab_size, embed_dim)
        self.rnn = nn.LSTM(embed_dim, hidden_dim, batch_first=False)
        self.fc = nn.Linear(hidden_dim, output_dim)

    def forward(self, text):
        # text 形状: (sent_len, batch_size)
        embedded = self.embedding(text) # 形状: (sent_len, batch_size, embed_dim)
        output, (hidden, cell) = self.rnn(embedded)
        # 我们取最后一个时间步的隐藏状态作为句子表示
        # hidden 形状: (1, batch_size, hidden_dim)
        hidden = hidden.squeeze(0) # 形状: (batch_size, hidden_dim)
        logits = self.fc(hidden) # 形状: (batch_size, output_dim)
        return logits
model = RNNClassifier(len(TEXT.vocab), EMBEDDING_DIM, HIDDEN_DIM, NUM_CLASSES).to(device)
```
在 `forward` 函数中，我们只使用了 LSTM 最后一个时间步的隐藏状态（`hidden`），然后通过一个全连接层得到分类逻辑值（logits）。这是一种典型的“多对一”处理方式。







---




## 6. 训练模型 🏋️






训练循环与我们之前见过的类似。我们使用交叉熵损失和 Adam 优化器。



以下是训练和评估函数：










```python
import torch.optim as optim
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(), lr=LEARNING_RATE)
def compute_accuracy(preds, y):
    _, predicted = torch.max(preds, 1)
    correct = (predicted == y).float()
    acc = correct.sum() / len(correct)
    return acc
def train(model, iterator, optimizer, criterion):
    model.train()
    epoch_loss = 0
    epoch_acc = 0
    for batch in iterator:
        text, labels = batch.review, batch.sentiment
        optimizer.zero_grad()
        predictions = model(text)
        loss = criterion(predictions, labels)
        acc = compute_accuracy(predictions, labels)
        loss.backward()
        optimizer.step()
        epoch_loss += loss.item()
        epoch_acc += acc.item()
    return epoch_loss / len(iterator), epoch_acc / len(iterator)
```
我们可以用类似的函数来评估验证集和测试集。




---








## 7. 对新文本进行预测 🔮







模型训练好后，我们需要能够对新的、未见过的文本进行预测。





以下是一个预测函数：





```python
def predict_sentiment(model, sentence, text_field, label_field, device):
    model.eval()
    # 分词并转换为索引
    tokenized = [tok.text for tok in spacy_en.tokenizer(sentence.lower())]
    indexed = [text_field.vocab.stoi[t] if t in text_field.vocab else text_field.vocab.stoi['<unk>'] for t in tokenized]
    tensor = torch.LongTensor(indexed).unsqueeze(1).to(device) # 形状: (sent_len, 1)
    with torch.no_grad():
        prediction = model(tensor)
        probabilities = torch.softmax(prediction, dim=1)
    # 获取正面情感的概率（假设索引1对应正面）
    positive_prob = probabilities[0][label_field.vocab.stoi['1']].item()
    return positive_prob
# 示例
sentence = "This is such an awesome movie, I really love it! 😊"
prob = predict_sentiment(model, sentence, TEXT, LABEL, device)
print(f"正面情感概率: {prob:.2%}")
```







---



## 8. 更高效的方法：Packed LSTM 🚀




上面介绍的是基础的 LSTM 实现。在实践中，为了处理不同长度的序列并减少计算浪费，我们可以使用 **Packed Sequence**。这种方法在内部对序列进行打包，跳过填充部分的计算，能显著提升训练速度。




主要改动在于数据加载和模型前向传播：
1.  在定义 `TEXT` 字段时，设置 `include_lengths=True` 以获取序列实际长度。
2.  在 `BucketIterator` 中设置 `sort_within_batch=True` 和 `sort_key`。
3.  在模型前向传播中，使用 `torch.nn.utils.rnn.pack_padded_sequence` 和 `torch.nn.utils.rnn.pad_packed_sequence`。





由于实现更为复杂，这里不展开代码细节，但它是处理变长序列的标准且高效的方法。







---






## 9. 总结 📝







本节课我们一起学习了如何在 PyTorch 中实现一个基于 LSTM 的情感分类器。我们涵盖了从使用 TorchText 和 SpaCy 进行数据加载与处理，到构建包含嵌入层、LSTM 层和全连接层的模型，再到训练模型并对新文本进行预测的完整流程。





关键点总结：
*   **数据处理**：使用 `Field` 定义数据处理方式，用 `TabularDataset` 加载数据，用 `BucketIterator` 创建高效的数据加载器。
*   **词汇表**：只在训练集上构建，并限制大小以防止过拟合。
*   **模型架构**：`Embedding -> LSTM -> Linear`，采用“多对一”结构，使用最后一个时间步的隐藏状态进行分类。
*   **训练**：标准的训练循环，使用交叉熵损失和 Adam 优化器。
*   **预测**：需要将新文本分词并转换为词汇表索引，再输入模型。
*   **高级优化**：提及了使用 Packed Sequence 来处理变长序列，以提高效率。


![](img/49104266c97f1f4f9793724450b9f7d0_389.png)

实现 RNN 文本分类涉及较多步骤，初次接触可能会感到复杂，这是完全正常的。希望本教程能为你提供一个坚实的起点和可用的代码模板。在接下来的课程中，我们将进入生成式模型的世界。