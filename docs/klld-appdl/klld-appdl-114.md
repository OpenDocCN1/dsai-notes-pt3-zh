# 114：L54.2 - 字节对编码（BPE）详解 🧩

![](img/8180bfe6a9e9bf5f58c1be893aad1086_1.png)

在本节课中，我们将要学习一种名为**字节对编码（Byte Pair Encoding, BPE）**的自然语言处理技术。BPE是一种用于创建子词单元的数据压缩算法，它能有效解决机器翻译等任务中因未知词过多而导致翻译质量下降的问题。我们将从BPE的基本概念出发，通过一个具体例子来理解其工作原理，并探讨它在实际应用中的优势。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_2.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_3.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_4.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_5.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_6.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_7.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_8.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_9.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_10.png)

---

![](img/8180bfe6a9e9bf5f58c1be893aad1086_11.png)

## 什么是字节对编码（BPE）？🤔

![](img/8180bfe6a9e9bf5f58c1be893aad1086_13.png)

上一节我们提到了未知词对翻译质量的影响。本节中，我们来看看BPE如何解决这个问题。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_14.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_15.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_16.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_17.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_18.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_19.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_20.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_21.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_22.png)

BPE是一种古老的**数据压缩算法**。在自然语言处理（NLP）或机器翻译的上下文中，一个“字节”通常指代一个**字符**或一串字符序列。BPE的核心思想是：**迭代地将序列中出现频率最高的字符对（或字节对）替换为一个新的、未使用过的符号**。通过这种方式，我们可以将字符合并，形成有意义的子词单元。这些子词单元不一定需要具备传统词典中的含义，只要它们对任务（如翻译）有用即可。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_23.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_24.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_26.png)

---

![](img/8180bfe6a9e9bf5f58c1be893aad1086_27.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_28.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_29.png)

## BPE算法流程与示例 📝

理解了BPE的基本概念后，本节我们通过一个具体例子来演示其算法流程。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_31.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_32.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_33.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_34.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_35.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_36.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_37.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_38.png)

假设我们有一个小型词典，包含以下单词及其在语料库中的出现频率：
*   `low`: 出现 5 次
*   `lower`: 出现 2 次
*   `newest`: 出现 6 次
*   `widest`: 出现 3 次

![](img/8180bfe6a9e9bf5f58c1be893aad1086_39.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_40.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_41.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_42.png)

首先，我们在每个单词的字符间添加空格，并在末尾添加一个特殊的“词尾”符号（例如 `</w>`）。处理后的初始状态如下：

```
l o w </w>
l o w e r </w>
n e w e s t </w>
w i d e s t </w>
```

![](img/8180bfe6a9e9bf5f58c1be893aad1086_44.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_45.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_46.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_47.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_48.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_49.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_50.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_51.png)

以下是BPE算法的核心步骤：

![](img/8180bfe6a9e9bf5f58c1be893aad1086_52.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_53.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_54.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_55.png)

1.  **统计频率**：统计所有相邻字符对的出现频率。
2.  **合并最高频对**：找到出现频率最高的字符对，将它们合并成一个新的符号。
3.  **重复迭代**：重复步骤1和2，直到达到预设的合并次数（这是一个超参数）。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_57.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_58.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_59.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_60.png)

让我们手动模拟这个过程：

![](img/8180bfe6a9e9bf5f58c1be893aad1086_61.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_62.png)

*   **第一轮合并**：统计发现，字符对 `e` 和 `s`（即 `es`）总共出现了 9 次（在 `newest` 和 `widest` 中），频率最高。我们将其合并为 `es`。
    ```
    l o w </w>
    l o w e r </w>
    n e w es t </w>
    w i d es t </w>
    ```
*   **第二轮合并**：现在，频率最高的字符对是 `es` 和 `t`（即 `est`），出现 9 次。将其合并为 `est`。
    ```
    l o w </w>
    l o w e r </w>
    n e w est </w>
    w i d est </w>
    ```
*   **第三轮合并**：接下来，`est` 和 `</w>`（词尾）出现频率高，将其合并为 `est</w>`。
    ```
    l o w </w>
    l o w e r </w>
    n e w est</w>
    w i d est</w>
    ```
*   **后续合并**：算法会继续合并，例如合并 `l` 和 `o` 成为 `lo`，然后是 `lo` 和 `w` 成为 `low`，等等。

经过多轮合并（次数由我们设定），我们最终会得到一个新的子词词典，例如：`low`, `low er</w>`, `new est</w>`, `wid est</w>`。这些子词单元就可以作为我们模型的新“词汇”进行词嵌入训练。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_64.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_65.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_66.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_67.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_68.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_69.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_70.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_71.png)

---

![](img/8180bfe6a9e9bf5f58c1be893aad1086_72.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_73.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_74.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_75.png)

## 如何处理未知词？❓

![](img/8180bfe6a9e9bf5f58c1be893aad1086_77.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_78.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_79.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_80.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_81.png)

上一节我们学习了如何在训练语料上构建BPE词典。本节中我们来看看，当模型遇到一个从未见过的单词（集外词）时该如何处理。

关键在于，我们在**训练阶段**不仅得到了最终的子词词典，还**记录下了所有合并操作的顺序**。在测试或推理阶段，对于任何新单词，我们只需按照训练时记录的顺序，依次尝试应用这些合并规则即可。

例如，假设新单词是 `lowest`，而我们的合并规则顺序是：1) 合并 `es`， 2) 合并 `est`， 3) 合并 `lo`， 4) 合并 `low`。

处理过程如下：
1.  `l o w e s t </w>` -> 应用规则1: `l o w es t </w>`
2.  `l o w es t </w>` -> 应用规则2: `l o w est </w>`
3.  `l o w est </w>` -> 应用规则3: `lo w est </w>`
4.  `lo w est </w>` -> 应用规则4: `low est </w>`

最终，`lowest` 被分解为 `low` 和 `est</w>`。这两个子词单元都存在于我们训练得到的词典中，因此这个新单词就不再是“未知词”了。

---

## BPE的优势与效果 ⚖️

了解了BPE如何处理新词后，本节我们总结一下它相比其他方法的优势。

在NLP中，我们通常在词级别和字符级别之间进行权衡：
*   **词级别模型**：词汇表可能非常庞大（例如数百万），且会遇到大量未知词。
*   **字符级别模型**：词汇表很小（例如几十个字符），但序列长度会变得极长，增加模型计算复杂度。

BPE在两者之间取得了很好的平衡。以下是一个对比示例：

| 方法 | 语料库序列长度（词符数） | 词汇表大小 | 未知词数量 |
| :--- | :--- | :--- | :--- |
| 词级别 | 1亿 | ~175万 | 很多 |
| 字符级别 | 爆炸性增长 | ~3000 | 0 |
| **BPE** | **相对合理** | **~6.3万** | **很少** |

BPE的优势在于：
1.  **大幅减少未知词**：通过将单词分解为子词，即使是新词也能被已有子词覆盖。
2.  **保持合理序列长度**：不像字符模型那样使序列过长。
3.  **跨语言有效性**：尤其对于德语、俄语等具有大量复合词的语言，BPE能有效地将其分解为有意义的组成部分（如词根、词缀）。
4.  **简单而强大**：算法易于理解和实现，效果显著。

---

## 总结 📚

本节课中我们一起学习了**字节对编码（BPE）**。我们从其作为数据压缩算法的起源讲起，详细分析了它通过迭代合并高频字符对来构建子词单元的工作流程，并通过实例进行了演示。我们还探讨了BPE如何处理训练时未见过的单词，以及它在词汇表大小和序列长度之间取得的优异平衡。BPE以其简单、优雅且强大的特性，已成为现代NLP模型（如BERT、GPT）中主流的文本预处理技术之一。