# P131：L15.7 - PyTorch 中的 RNN 情感分类器 🎬

![](img/49104266c97f1f4f9793724450b9f7d0_1.png)

![](img/49104266c97f1f4f9793724450b9f7d0_2.png)

![](img/49104266c97f1f4f9793724450b9f7d0_3.png)

![](img/49104266c97f1f4f9793724450b9f7d0_4.png)

![](img/49104266c97f1f4f9793724450b9f7d0_6.png)

![](img/49104266c97f1f4f9793724450b9f7d0_8.png)

![](img/49104266c97f1f4f9793724450b9f7d0_9.png)

![](img/49104266c97f1f4f9793724450b9f7d0_10.png)

在本节课中，我们将学习如何在 PyTorch 中实现一个用于情感分类的循环神经网络。我们将使用一个“多对一”的 RNN 架构，将一段文本（如电影评论）作为输入，并输出一个类别标签（如正面或负面情感）。我们将从数据准备、模型构建到训练和预测，完整地走一遍流程。

![](img/49104266c97f1f4f9793724450b9f7d0_12.png)

![](img/49104266c97f1f4f9793724450b9f7d0_14.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_16.png)

![](img/49104266c97f1f4f9793724450b9f7d0_18.png)

![](img/49104266c97f1f4f9793724450b9f7d0_20.png)

![](img/49104266c97f1f4f9793724450b9f7d0_22.png)

## 1. 概述与准备工作 📋

![](img/49104266c97f1f4f9793724450b9f7d0_24.png)

![](img/49104266c97f1f4f9793724450b9f7d0_26.png)

![](img/49104266c97f1f4f9793724450b9f7d0_28.png)

上一节我们介绍了“多对一”RNN的基本概念。本节中，我们来看看如何用 PyTorch 和 TorchText 库具体实现一个情感分类器。

![](img/49104266c97f1f4f9793724450b9f7d0_30.png)

![](img/49104266c97f1f4f9793724450b9f7d0_32.png)

![](img/49104266c97f1f4f9793724450b9f7d0_34.png)

![](img/49104266c97f1f4f9793724450b9f7d0_35.png)

首先，我们需要设置一些通用参数并导入必要的库。

![](img/49104266c97f1f4f9793724450b9f7d0_37.png)

![](img/49104266c97f1f4f9793724450b9f7d0_38.png)

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

![](img/49104266c97f1f4f9793724450b9f7d0_40.png)

![](img/49104266c97f1f4f9793724450b9f7d0_42.png)

![](img/49104266c97f1f4f9793724450b9f7d0_44.png)

![](img/49104266c97f1f4f9793724450b9f7d0_45.png)

![](img/49104266c97f1f4f9793724450b9f7d0_46.png)

我们将使用 IMDB 电影评论数据集。为了简化预处理步骤，我们从指定链接下载一个已处理好的版本。

![](img/49104266c97f1f4f9793724450b9f7d0_48.png)

![](img/49104266c97f1f4f9793724450b9f7d0_50.png)

```python
import pandas as pd
import torch
import torchtext
from torchtext.legacy import data
import spacy

![](img/49104266c97f1f4f9793724450b9f7d0_52.png)

# 下载并加载数据集
df = pd.read_csv('imdb_dataset.csv')
# 为保持代码一致性，重命名列
TEXT_COLUMN_NAME = 'review'
LABEL_COLUMN_NAME = 'sentiment'
df = df.rename(columns={df.columns[0]: TEXT_COLUMN_NAME, df.columns[1]: LABEL_COLUMN_NAME})
```

![](img/49104266c97f1f4f9793724450b9f7d0_54.png)

![](img/49104266c97f1f4f9793724450b9f7d0_56.png)

![](img/49104266c97f1f4f9793724450b9f7d0_58.png)

![](img/49104266c97f1f4f9793724450b9f7d0_59.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_61.png)

![](img/49104266c97f1f4f9793724450b9f7d0_62.png)

![](img/49104266c97f1f4f9793724450b9f7d0_64.png)

![](img/49104266c97f1f4f9793724450b9f7d0_66.png)

![](img/49104266c97f1f4f9793724450b9f7d0_68.png)

## 2. 使用 TorchText 处理数据 🔧

![](img/49104266c97f1f4f9793724450b9f7d0_70.png)

![](img/49104266c97f1f4f9793724450b9f7d0_72.png)

![](img/49104266c97f1f4f9793724450b9f7d0_74.png)

现在，我们需要将原始文本数据转换为模型可以处理的格式。我们将使用 SpaCy 进行分词，并使用 TorchText 的 `legacy` API 来构建数据管道。

![](img/49104266c97f1f4f9793724450b9f7d0_76.png)

![](img/49104266c97f1f4f9793724450b9f7d0_77.png)

![](img/49104266c97f1f4f9793724450b9f7d0_79.png)

首先，定义用于处理文本和标签的 `Field`。

![](img/49104266c97f1f4f9793724450b9f7d0_81.png)

![](img/49104266c97f1f4f9793724450b9f7d0_83.png)

![](img/49104266c97f1f4f9793724450b9f7d0_84.png)

![](img/49104266c97f1f4f9793724450b9f7d0_86.png)

![](img/49104266c97f1f4f9793724450b9f7d0_87.png)

```python
# 加载 SpaCy 英语分词器
spacy_en = spacy.load('en_core_web_sm')
def tokenizer(text):
    return [tok.text for tok in spacy_en.tokenizer(text)]

![](img/49104266c97f1f4f9793724450b9f7d0_89.png)

![](img/49104266c97f1f4f9793724450b9f7d0_91.png)

![](img/49104266c97f1f4f9793724450b9f7d0_93.png)

![](img/49104266c97f1f4f9793724450b9f7d0_95.png)

# 定义字段
TEXT = data.Field(tokenize=tokenizer, lower=True, include_lengths=False)
LABEL = data.LabelField(dtype=torch.long)
```

![](img/49104266c97f1f4f9793724450b9f7d0_97.png)

![](img/49104266c97f1f4f9793724450b9f7d0_99.png)

![](img/49104266c97f1f4f9793724450b9f7d0_101.png)

接下来，使用 `TabularDataset` 加载我们的 CSV 文件，并按照指定字段进行解析。

![](img/49104266c97f1f4f9793724450b9f7d0_103.png)

![](img/49104266c97f1f4f9793724450b9f7d0_105.png)

```python
fields = [(TEXT_COLUMN_NAME, TEXT), (LABEL_COLUMN_NAME, LABEL)]
dataset = data.TabularDataset(
    path='imdb_dataset.csv',
    format='csv',
    fields=fields,
    skip_header=True
)
```

![](img/49104266c97f1f4f9793724450b9f7d0_107.png)

然后，我们将数据集分割为训练集、验证集和测试集。

![](img/49104266c97f1f4f9793724450b9f7d0_108.png)

![](img/49104266c97f1f4f9793724450b9f7d0_110.png)

![](img/49104266c97f1f4f9793724450b9f7d0_112.png)

![](img/49104266c97f1f4f9793724450b9f7d0_114.png)

![](img/49104266c97f1f4f9793724450b9f7d0_116.png)

```python
# 首先分割出测试集
train_data, test_data = dataset.split(split_ratio=0.8)
# 再从训练集中分割出验证集
train_data, valid_data = train_data.split(split_ratio=0.85)
print(f'训练集: {len(train_data)}')
print(f'验证集: {len(valid_data)}')
print(f'测试集: {len(test_data)}')
```

![](img/49104266c97f1f4f9793724450b9f7d0_117.png)

![](img/49104266c97f1f4f9793724450b9f7d0_119.png)

![](img/49104266c97f1f4f9793724450b9f7d0_121.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_123.png)

![](img/49104266c97f1f4f9793724450b9f7d0_124.png)

![](img/49104266c97f1f4f9793724450b9f7d0_126.png)

![](img/49104266c97f1f4f9793724450b9f7d0_127.png)

## 3. 构建词汇表 📚

![](img/49104266c97f1f4f9793724450b9f7d0_129.png)

![](img/49104266c97f1f4f9793724450b9f7d0_131.png)

词汇表将每个单词映射到一个唯一的整数索引。我们只在训练集上构建词汇表，以防止信息从验证集和测试集泄露。

![](img/49104266c97f1f4f9793724450b9f7d0_133.png)

![](img/49104266c97f1f4f9793724450b9f7d0_134.png)

![](img/49104266c97f1f4f9793724450b9f7d0_136.png)

![](img/49104266c97f1f4f9793724450b9f7d0_138.png)

![](img/49104266c97f1f4f9793724450b9f7d0_140.png)

以下是构建词汇表的步骤：
```python
# 基于训练集构建词汇表，并限制最常出现的20000个词
TEXT.build_vocab(train_data, max_size=VOCAB_SIZE)
LABEL.build_vocab(train_data)

![](img/49104266c97f1f4f9793724450b9f7d0_142.png)

![](img/49104266c97f1f4f9793724450b9f7d0_144.png)

![](img/49104266c97f1f4f9793724450b9f7d0_146.png)

print(f"词汇表大小: {len(TEXT.vocab)}")
print(f"类别: {LABEL.vocab.stoi}")
```
词汇表大小会是 `VOCAB_SIZE + 2`，因为包含了 `<unk>`（未知词）和 `<pad>`（填充）两个特殊标记。

![](img/49104266c97f1f4f9793724450b9f7d0_148.png)

![](img/49104266c97f1f4f9793724450b9f7d0_150.png)

![](img/49104266c97f1f4f9793724450b9f7d0_152.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_154.png)

![](img/49104266c97f1f4f9793724450b9f7d0_156.png)

## 4. 创建数据加载器 ⚙️

![](img/49104266c97f1f4f9793724450b9f7d0_158.png)

![](img/49104266c97f1f4f9793724450b9f7d0_160.png)

![](img/49104266c97f1f4f9793724450b9f7d0_162.png)

为了高效训练，我们使用 TorchText 的 `BucketIterator`。它会将长度相近的句子分到同一个批次中，从而减少所需的填充（padding）量，提升计算效率。

![](img/49104266c97f1f4f9793724450b9f7d0_164.png)

![](img/49104266c97f1f4f9793724450b9f7d0_166.png)

![](img/49104266c97f1f4f9793724450b9f7d0_168.png)

![](img/49104266c97f1f4f9793724450b9f7d0_170.png)

![](img/49104266c97f1f4f9793724450b9f7d0_172.png)

![](img/49104266c97f1f4f9793724450b9f7d0_174.png)

```python
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')

![](img/49104266c97f1f4f9793724450b9f7d0_176.png)

![](img/49104266c97f1f4f9793724450b9f7d0_178.png)

![](img/49104266c97f1f4f9793724450b9f7d0_179.png)

![](img/49104266c97f1f4f9793724450b9f7d0_181.png)

![](img/49104266c97f1f4f9793724450b9f7d0_183.png)

![](img/49104266c97f1f4f9793724450b9f7d0_185.png)

![](img/49104266c97f1f4f9793724450b9f7d0_187.png)

train_loader, valid_loader, test_loader = data.BucketIterator.splits(
    (train_data, valid_data, test_data),
    batch_size=BATCH_SIZE,
    sort_within_batch=True,
    sort_key=lambda x: len(x.text),
    device=device
)
```

![](img/49104266c97f1f4f9793724450b9f7d0_189.png)

![](img/49104266c97f1f4f9793724450b9f7d0_191.png)

![](img/49104266c97f1f4f9793724450b9f7d0_193.png)

让我们检查一下第一个批次的数据形状，确保一切正常。
```python
for batch in train_loader:
    text, labels = batch.review, batch.sentiment
    print(f'文本张量形状: {text.shape}') # (句子长度, 批次大小)
    print(f'标签张量形状: {labels.shape}') # (批次大小,)
    break
```
注意，RNN 输入的张量形状通常是 `(序列长度, 批次大小)`，这与卷积网络不同。

![](img/49104266c97f1f4f9793724450b9f7d0_195.png)

![](img/49104266c97f1f4f9793724450b9f7d0_196.png)

![](img/49104266c97f1f4f9793724450b9f7d0_198.png)

![](img/49104266c97f1f4f9793724450b9f7d0_200.png)

![](img/49104266c97f1f4f9793724450b9f7d0_201.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_203.png)

## 5. 构建 LSTM 模型 🧠

![](img/49104266c97f1f4f9793724450b9f7d0_205.png)

![](img/49104266c97f1f4f9793724450b9f7d0_207.png)

![](img/49104266c97f1f4f9793724450b9f7d0_208.png)

![](img/49104266c97f1f4f9793724450b9f7d0_210.png)

![](img/49104266c97f1f4f9793724450b9f7d0_212.png)

我们的模型将包含三个主要部分：嵌入层（Embedding Layer）、LSTM 层和全连接输出层。

![](img/49104266c97f1f4f9793724450b9f7d0_214.png)

![](img/49104266c97f1f4f9793724450b9f7d0_215.png)

![](img/49104266c97f1f4f9793724450b9f7d0_217.png)

![](img/49104266c97f1f4f9793724450b9f7d0_219.png)

![](img/49104266c97f1f4f9793724450b9f7d0_221.png)

![](img/49104266c97f1f4f9793724450b9f7d0_223.png)

以下是模型的定义：
```python
import torch.nn as nn

![](img/49104266c97f1f4f9793724450b9f7d0_225.png)

![](img/49104266c97f1f4f9793724450b9f7d0_227.png)

![](img/49104266c97f1f4f9793724450b9f7d0_229.png)

![](img/49104266c97f1f4f9793724450b9f7d0_231.png)

![](img/49104266c97f1f4f9793724450b9f7d0_233.png)

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

![](img/49104266c97f1f4f9793724450b9f7d0_235.png)

![](img/49104266c97f1f4f9793724450b9f7d0_237.png)

![](img/49104266c97f1f4f9793724450b9f7d0_238.png)

model = RNNClassifier(len(TEXT.vocab), EMBEDDING_DIM, HIDDEN_DIM, NUM_CLASSES).to(device)
```
在 `forward` 函数中，我们只使用了 LSTM 最后一个时间步的隐藏状态（`hidden`），然后通过一个全连接层得到分类逻辑值（logits）。这是一种典型的“多对一”处理方式。

![](img/49104266c97f1f4f9793724450b9f7d0_240.png)

![](img/49104266c97f1f4f9793724450b9f7d0_241.png)

![](img/49104266c97f1f4f9793724450b9f7d0_243.png)

![](img/49104266c97f1f4f9793724450b9f7d0_245.png)

![](img/49104266c97f1f4f9793724450b9f7d0_247.png)

![](img/49104266c97f1f4f9793724450b9f7d0_249.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_251.png)

![](img/49104266c97f1f4f9793724450b9f7d0_253.png)

![](img/49104266c97f1f4f9793724450b9f7d0_255.png)

## 6. 训练模型 🏋️

![](img/49104266c97f1f4f9793724450b9f7d0_257.png)

![](img/49104266c97f1f4f9793724450b9f7d0_258.png)

![](img/49104266c97f1f4f9793724450b9f7d0_260.png)

![](img/49104266c97f1f4f9793724450b9f7d0_261.png)

![](img/49104266c97f1f4f9793724450b9f7d0_262.png)

训练循环与我们之前见过的类似。我们使用交叉熵损失和 Adam 优化器。

![](img/49104266c97f1f4f9793724450b9f7d0_264.png)

![](img/49104266c97f1f4f9793724450b9f7d0_266.png)

以下是训练和评估函数：
```python
import torch.optim as optim
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(), lr=LEARNING_RATE)

![](img/49104266c97f1f4f9793724450b9f7d0_268.png)

![](img/49104266c97f1f4f9793724450b9f7d0_270.png)

![](img/49104266c97f1f4f9793724450b9f7d0_271.png)

def compute_accuracy(preds, y):
    _, predicted = torch.max(preds, 1)
    correct = (predicted == y).float()
    acc = correct.sum() / len(correct)
    return acc

![](img/49104266c97f1f4f9793724450b9f7d0_273.png)

![](img/49104266c97f1f4f9793724450b9f7d0_275.png)

![](img/49104266c97f1f4f9793724450b9f7d0_277.png)

![](img/49104266c97f1f4f9793724450b9f7d0_278.png)

![](img/49104266c97f1f4f9793724450b9f7d0_279.png)

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

![](img/49104266c97f1f4f9793724450b9f7d0_281.png)

![](img/49104266c97f1f4f9793724450b9f7d0_283.png)

![](img/49104266c97f1f4f9793724450b9f7d0_285.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_287.png)

![](img/49104266c97f1f4f9793724450b9f7d0_288.png)

![](img/49104266c97f1f4f9793724450b9f7d0_289.png)

![](img/49104266c97f1f4f9793724450b9f7d0_290.png)

![](img/49104266c97f1f4f9793724450b9f7d0_291.png)

![](img/49104266c97f1f4f9793724450b9f7d0_293.png)

![](img/49104266c97f1f4f9793724450b9f7d0_294.png)

## 7. 对新文本进行预测 🔮

![](img/49104266c97f1f4f9793724450b9f7d0_296.png)

![](img/49104266c97f1f4f9793724450b9f7d0_298.png)

![](img/49104266c97f1f4f9793724450b9f7d0_299.png)

![](img/49104266c97f1f4f9793724450b9f7d0_301.png)

![](img/49104266c97f1f4f9793724450b9f7d0_302.png)

![](img/49104266c97f1f4f9793724450b9f7d0_304.png)

模型训练好后，我们需要能够对新的、未见过的文本进行预测。

![](img/49104266c97f1f4f9793724450b9f7d0_306.png)

![](img/49104266c97f1f4f9793724450b9f7d0_307.png)

![](img/49104266c97f1f4f9793724450b9f7d0_309.png)

![](img/49104266c97f1f4f9793724450b9f7d0_311.png)

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

![](img/49104266c97f1f4f9793724450b9f7d0_313.png)

![](img/49104266c97f1f4f9793724450b9f7d0_315.png)

![](img/49104266c97f1f4f9793724450b9f7d0_317.png)

![](img/49104266c97f1f4f9793724450b9f7d0_318.png)

# 示例
sentence = "This is such an awesome movie, I really love it! 😊"
prob = predict_sentiment(model, sentence, TEXT, LABEL, device)
print(f"正面情感概率: {prob:.2%}")
```

![](img/49104266c97f1f4f9793724450b9f7d0_320.png)

![](img/49104266c97f1f4f9793724450b9f7d0_322.png)

![](img/49104266c97f1f4f9793724450b9f7d0_324.png)

![](img/49104266c97f1f4f9793724450b9f7d0_326.png)

![](img/49104266c97f1f4f9793724450b9f7d0_328.png)

![](img/49104266c97f1f4f9793724450b9f7d0_330.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_332.png)

![](img/49104266c97f1f4f9793724450b9f7d0_333.png)

## 8. 更高效的方法：Packed LSTM 🚀

![](img/49104266c97f1f4f9793724450b9f7d0_335.png)

![](img/49104266c97f1f4f9793724450b9f7d0_337.png)

![](img/49104266c97f1f4f9793724450b9f7d0_339.png)

上面介绍的是基础的 LSTM 实现。在实践中，为了处理不同长度的序列并减少计算浪费，我们可以使用 **Packed Sequence**。这种方法在内部对序列进行打包，跳过填充部分的计算，能显著提升训练速度。

![](img/49104266c97f1f4f9793724450b9f7d0_341.png)

![](img/49104266c97f1f4f9793724450b9f7d0_343.png)

![](img/49104266c97f1f4f9793724450b9f7d0_345.png)

主要改动在于数据加载和模型前向传播：
1.  在定义 `TEXT` 字段时，设置 `include_lengths=True` 以获取序列实际长度。
2.  在 `BucketIterator` 中设置 `sort_within_batch=True` 和 `sort_key`。
3.  在模型前向传播中，使用 `torch.nn.utils.rnn.pack_padded_sequence` 和 `torch.nn.utils.rnn.pad_packed_sequence`。

![](img/49104266c97f1f4f9793724450b9f7d0_347.png)

![](img/49104266c97f1f4f9793724450b9f7d0_348.png)

![](img/49104266c97f1f4f9793724450b9f7d0_350.png)

![](img/49104266c97f1f4f9793724450b9f7d0_352.png)

由于实现更为复杂，这里不展开代码细节，但它是处理变长序列的标准且高效的方法。

![](img/49104266c97f1f4f9793724450b9f7d0_354.png)

![](img/49104266c97f1f4f9793724450b9f7d0_356.png)

![](img/49104266c97f1f4f9793724450b9f7d0_358.png)

![](img/49104266c97f1f4f9793724450b9f7d0_359.png)

![](img/49104266c97f1f4f9793724450b9f7d0_361.png)

![](img/49104266c97f1f4f9793724450b9f7d0_362.png)

---

![](img/49104266c97f1f4f9793724450b9f7d0_364.png)

![](img/49104266c97f1f4f9793724450b9f7d0_365.png)

![](img/49104266c97f1f4f9793724450b9f7d0_367.png)

![](img/49104266c97f1f4f9793724450b9f7d0_369.png)

![](img/49104266c97f1f4f9793724450b9f7d0_371.png)

## 9. 总结 📝

![](img/49104266c97f1f4f9793724450b9f7d0_372.png)

![](img/49104266c97f1f4f9793724450b9f7d0_373.png)

![](img/49104266c97f1f4f9793724450b9f7d0_375.png)

![](img/49104266c97f1f4f9793724450b9f7d0_377.png)

![](img/49104266c97f1f4f9793724450b9f7d0_379.png)

![](img/49104266c97f1f4f9793724450b9f7d0_380.png)

本节课我们一起学习了如何在 PyTorch 中实现一个基于 LSTM 的情感分类器。我们涵盖了从使用 TorchText 和 SpaCy 进行数据加载与处理，到构建包含嵌入层、LSTM 层和全连接层的模型，再到训练模型并对新文本进行预测的完整流程。

![](img/49104266c97f1f4f9793724450b9f7d0_382.png)

![](img/49104266c97f1f4f9793724450b9f7d0_383.png)

![](img/49104266c97f1f4f9793724450b9f7d0_384.png)

![](img/49104266c97f1f4f9793724450b9f7d0_386.png)

关键点总结：
*   **数据处理**：使用 `Field` 定义数据处理方式，用 `TabularDataset` 加载数据，用 `BucketIterator` 创建高效的数据加载器。
*   **词汇表**：只在训练集上构建，并限制大小以防止过拟合。
*   **模型架构**：`Embedding -> LSTM -> Linear`，采用“多对一”结构，使用最后一个时间步的隐藏状态进行分类。
*   **训练**：标准的训练循环，使用交叉熵损失和 Adam 优化器。
*   **预测**：需要将新文本分词并转换为词汇表索引，再输入模型。
*   **高级优化**：提及了使用 Packed Sequence 来处理变长序列，以提高效率。

![](img/49104266c97f1f4f9793724450b9f7d0_387.png)

![](img/49104266c97f1f4f9793724450b9f7d0_389.png)

实现 RNN 文本分类涉及较多步骤，初次接触可能会感到复杂，这是完全正常的。希望本教程能为你提供一个坚实的起点和可用的代码模板。在接下来的课程中，我们将进入生成式模型的世界。