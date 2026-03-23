# 002：从零实现RL for LLM

![](img/d02571479e786eb95b2441c98cd25afc_1.png)

![](img/d02571479e786eb95b2441c98cd25afc_3.png)

在本节课中，我们将开始实现之前解释的所有目标函数。我们将从加载模型、计算对数概率开始，逐步构建完整的强化学习训练循环。

## 加载模型与准备数据

上一节我们介绍了强化学习的目标函数。本节中，我们来看看如何加载模型并准备数据。

首先，我们需要加载模型。我们将使用 Hugging Face Transformers 库。

```python
from transformers import AutoModelForCausalLM

model_name = "google/gemma-2b"
model = AutoModelForCausalLM.from_pretrained(
    model_name,
    torch_dtype=torch.bfloat16,
    device_map="cuda:0",
    attn_implementation="flash_attention_2"
)
```

接下来，我们准备一个简单的示例数据来理解如何计算对数概率。

```python
from transformers import AutoTokenizer

![](img/d02571479e786eb95b2441c98cd25afc_5.png)

tokenizer = AutoTokenizer.from_pretrained(model_name)
texts = ["Hello world", "How are you"]
inputs = tokenizer(texts, padding=True, return_tensors="pt").to("cuda")
```

以下是准备输入、注意力掩码和标签的步骤：

1.  **输入ID**：将文本转换为模型可以理解的数字序列。
2.  **注意力掩码**：指示哪些是真实标记，哪些是填充标记。
3.  **标签**：用于计算损失的目标序列。对于因果语言建模，标签通常与输入ID相同，但填充部分需要特殊处理。

```python
input_ids = inputs["input_ids"]
attention_mask = inputs["attention_mask"]
labels = input_ids.clone()
# 将填充标记的标签设置为-100，以便在计算损失时忽略它们
labels[attention_mask == 0] = -100
```

## 计算对数概率

![](img/d02571479e786eb95b2441c98cd25afc_7.png)

现在我们已经准备好了数据，接下来看看如何计算模型生成特定标记序列的对数概率。

首先，我们将输入传递给模型以获得逻辑值。

```python
with torch.no_grad():
    outputs = model(input_ids=input_ids, attention_mask=attention_mask, use_cache=False)
logits = outputs.logits  # 形状: [batch_size, sequence_length, vocab_size]
```

由于我们进行的是下一个标记预测，因此需要将逻辑值和标签进行对齐。

```python
# 将标签向左移动一位，以与预测的下一个标记对齐
shift_labels = labels[..., 1:].contiguous()
# 逻辑值也需要相应地调整，忽略最后一个标记的预测
shift_logits = logits[..., :-1, :].contiguous()
```

接下来，我们计算对数概率。为了提高数值稳定性，我们使用 `log_softmax`。

![](img/d02571479e786eb95b2441c98cd25afc_9.png)

![](img/d02571479e786eb95b2441c98cd25afc_11.png)

```python
log_probs = torch.nn.functional.log_softmax(shift_logits, dim=-1)
```

然后，我们使用 `gather` 函数选择与标签对应的对数概率。

```python
# 创建掩码，忽略标签为-100的位置
label_mask = shift_labels != -100
# 将无效标签暂时设为0，以便进行gather操作
valid_shift_labels = shift_labels.clone()
valid_shift_labels[~label_mask] = 0
# 收集对应标签的对数概率
selected_log_probs = torch.gather(log_probs, -1, valid_shift_labels.unsqueeze(-1)).squeeze(-1)
# 应用掩码，将无效位置的对数概率设为0
selected_log_probs = selected_log_probs * label_mask
```

## 准备训练数据

在实际训练中，数据来自VLLM生成的轨迹。我们需要将这些轨迹转换为模型输入。

![](img/d02571479e786eb95b2441c98cd25afc_13.png)

![](img/d02571479e786eb95b2441c98cd25afc_15.png)

以下是准备模型输入的函数，它处理查询、响应和优势值。

![](img/d02571479e786eb95b2441c98cd25afc_17.png)

![](img/d02571479e786eb95b2441c98cd25afc_18.png)

![](img/d02571479e786eb95b2441c98cd25afc_19.png)

![](img/d02571479e786eb95b2441c98cd25afc_21.png)

![](img/d02571479e786eb95b2441c98cd25afc_23.png)

![](img/d02571479e786eb95b2441c98cd25afc_25.png)

![](img/d02571479e786eb95b2441c98cd25afc_26.png)

```python
def prepare_model_inputs(query_token_ids, response_token_ids, advantages, device="cuda"):
    batch_size = len(query_token_ids)
    combined_ids = [q + r for q, r in zip(query_token_ids, response_token_ids)]
    max_len = max(len(ids) for ids in combined_ids)

    pad_token_id = tokenizer.pad_token_id
    ignore_index = -100

    input_ids_list = []
    attention_mask_list = []
    labels_list = []
    advantages_list = []

    for i in range(batch_size):
        combined = combined_ids[i]
        num_pads = max_len - len(combined)

        # 输入ID和注意力掩码
        input_ids = combined + [pad_token_id] * num_pads
        attention_mask = [1] * len(combined) + [0] * num_pads

        # 标签：忽略查询部分和填充部分
        labels = [ignore_index] * len(query_token_ids[i]) + response_token_ids[i] + [ignore_index] * num_pads

        # 优势值：仅响应部分有值，查询和填充部分为0
        adv = [0.0] * len(query_token_ids[i]) + advantages[i] + [0.0] * num_pads

        input_ids_list.append(input_ids)
        attention_mask_list.append(attention_mask)
        labels_list.append(labels)
        advantages_list.append(adv)

    # 转换为张量
    input_ids = torch.tensor(input_ids_list, dtype=torch.long, device=device)
    attention_mask = torch.tensor(attention_mask_list, dtype=torch.long, device=device)
    labels = torch.tensor(labels_list, dtype=torch.long, device=device)
    advantages = torch.tensor(advantages_list, dtype=torch.float32, device=device)

    return {
        "input_ids": input_ids,
        "attention_mask": attention_mask,
        "labels": labels,
        "advantages": advantages
    }
```

![](img/d02571479e786eb95b2441c98cd25afc_28.png)

![](img/d02571479e786eb95b2441c98cd25afc_29.png)

![](img/d02571479e786eb95b2441c98cd25afc_31.png)

## 计算策略损失

![](img/d02571479e786eb95b2441c98cd25afc_33.png)

![](img/d02571479e786eb95b2441c98cd25afc_35.png)

![](img/d02571479e786eb95b2441c98cd25afc_36.png)

![](img/d02571479e786eb95b2441c98cd25afc_38.png)

现在我们已经能够计算对数概率并准备数据，接下来实现完整的策略损失函数。

![](img/d02571479e786eb95b2441c98cd25afc_40.png)

策略损失由两部分组成：策略梯度项和KL散度惩罚项。

**目标函数公式**：
`L = E[log π(a|s) * A] - β * KL(π || π_ref)`

其中：
*   `π` 是当前策略。
*   `π_ref` 是参考策略（通常是初始预训练模型）。
*   `A` 是优势值。
*   `β` 是KL散度系数。

以下是计算策略损失的函数实现。

![](img/d02571479e786eb95b2441c98cd25afc_42.png)

![](img/d02571479e786eb95b2441c98cd25afc_44.png)

![](img/d02571479e786eb95b2441c98cd25afc_46.png)

```python
def compute_policy_loss(inputs, policy_model, ref_model, total_response_tokens, temperature=1.0, kl_coef=0.01):
    input_ids = inputs["input_ids"]
    attention_mask = inputs["attention_mask"]
    labels = inputs["labels"]
    advantages = inputs["advantages"]

    # 计算标签掩码（忽略填充部分）
    shift_labels = labels[..., 1:].contiguous()
    label_mask = (shift_labels != -100).float()

    # 计算参考策略的对数概率
    with torch.no_grad():
        ref_log_probs = compute_log_probs(ref_model, inputs, temperature)

    # 计算当前策略的对数概率
    policy_log_probs = compute_log_probs(policy_model, inputs, temperature)

    # 对齐优势值
    shift_advantages = advantages[..., 1:].contiguous()

    # 策略梯度项
    policy_loss = - (policy_log_probs * shift_advantages * label_mask).sum() / total_response_tokens

    # KL散度惩罚项
    log_ratio = ref_log_probs - policy_log_probs
    kl_penalty = (torch.exp(log_ratio) - log_ratio - 1) * label_mask
    kl_penalty = kl_penalty.sum() / total_response_tokens

    # 总损失
    total_loss = policy_loss + kl_coef * kl_penalty

    return total_loss, kl_penalty
```

## 实现训练循环

我们已经有了损失函数，现在可以构建完整的训练循环了。

![](img/d02571479e786eb95b2441c98cd25afc_48.png)

训练循环的主要步骤包括：
1.  从数据集中采样提示。
2.  使用VLLM生成响应。
3.  计算优势值并创建训练数据。
4.  准备模型输入。
5.  执行梯度累积和优化步骤。
6.  更新VLLM中的模型权重。

![](img/d02571479e786eb95b2441c98cd25afc_50.png)

![](img/d02571479e786eb95b2441c98cd25afc_52.png)

![](img/d02571479e786eb95b2441c98cd25afc_54.png)

![](img/d02571479e786eb95b2441c98cd25afc_56.png)

以下是训练循环的核心代码结构。

![](img/d02571479e786eb95b2441c98cd25afc_58.png)

![](img/d02571479e786eb95b2441c98cd25afc_60.png)

![](img/d02571479e786eb95b2441c98cd25afc_62.png)

![](img/d02571479e786eb95b2441c98cd25afc_63.png)

![](img/d02571479e786eb95b2441c98cd25afc_65.png)

![](img/d02571479e786eb95b2441c98cd25afc_67.png)

![](img/d02571479e786eb95b2441c98cd25afc_69.png)

```python
# 初始化模型和优化器
policy_model = AutoModelForCausalLM.from_pretrained(...)
ref_model = AutoModelForCausalLM.from_pretrained(...)
optimizer = torch.optim.Adam(policy_model.parameters(), lr=1e-6)

![](img/d02571479e786eb95b2441c98cd25afc_71.png)

![](img/d02571479e786eb95b2441c98cd25afc_73.png)

![](img/d02571479e786eb95b2441c98cd25afc_75.png)

![](img/d02571479e786eb95b2441c98cd25afc_77.png)

![](img/d02571479e786eb95b2441c98cd25afc_78.png)

![](img/d02571479e786eb95b2441c98cd25afc_80.png)

![](img/d02571479e786eb95b2441c98cd25afc_82.png)

![](img/d02571479e786eb95b2441c98cd25afc_84.png)

![](img/d02571479e786eb95b2441c98cd25afc_86.png)

![](img/d02571479e786eb95b2441c98cd25afc_88.png)

![](img/d02571479e786eb95b2441c98cd25afc_90.png)

# 初始化VLLM推理引擎
from vllm import LLM
inference_engine = LLM(model="path/to/model", ...)

![](img/d02571479e786eb95b2441c98cd25afc_92.png)

![](img/d02571479e786eb95b2441c98cd25afc_93.png)

![](img/d02571479e786eb95b2441c98cd25afc_95.png)

![](img/d02571479e786eb95b2441c98cd25afc_97.png)

for iteration in range(total_iterations):
    # 1. 采样提示
    prompts = sample_prompts(dataset, batch_size)

    # 2. 使用VLLM生成响应
    generations = inference_engine.generate(prompts, ...)

    # 3. 计算优势值并创建训练数据
    episodes = create_training_episodes(prompts, generations)

    # 4. 准备模型输入
    inputs = prepare_model_inputs(episodes)

    # 5. 将VLLM置于睡眠模式以释放内存
    inference_engine.sleep()

    # 6. 执行梯度累积
    total_response_tokens = compute_total_tokens(episodes)
    for micro_batch in split_into_micro_batches(inputs, micro_batch_size):
        loss, kl = compute_policy_loss(micro_batch, policy_model, ref_model, total_response_tokens)
        loss.backward()

    # 7. 优化步骤
    optimizer.step()
    optimizer.zero_grad()

    # 8. 更新VLLM中的模型权重
    load_model_into_vllm(policy_model, inference_engine)
    inference_engine.wake_up()
```

![](img/d02571479e786eb95b2441c98cd25afc_99.png)

## 实验与想法

![](img/d02571479e786eb95b2441c98cd25afc_101.png)

在实现完整的训练流程后，我们可以尝试一些改进想法：

1.  **调整温度**：尝试不同的采样温度，观察对探索和性能的影响。
2.  **KL系数调度**：动态调整KL散度系数，例如在训练初期使用较大的系数，后期逐渐减小。
3.  **折扣因子**：为优势值引入折扣因子，鼓励模型使用更少的标记解决问题。
4.  **熵奖励**：在目标函数中添加熵奖励，以鼓励探索。
5.  **不同任务**：将方法应用于其他任务，如代码生成、数学推理或对话。
6.  **提示工程**：尝试不同的提示模板，观察对推理过程出现的影响。
7.  **离线更新**：实现PPO风格的裁剪目标函数，比较在线和离线更新的效果。

![](img/d02571479e786eb95b2441c98cd25afc_103.png)

![](img/d02571479e786eb95b2441c98cd25afc_104.png)

![](img/d02571479e786eb95b2441c98cd25afc_105.png)

![](img/d02571479e786eb95b2441c98cd25afc_106.png)

## 总结

![](img/d02571479e786eb95b2441c98cd25afc_108.png)

![](img/d02571479e786eb95b2441c98cd25afc_110.png)

![](img/d02571479e786eb95b2441c98cd25afc_112.png)

![](img/d02571479e786eb95b2441c98cd25afc_113.png)

![](img/d02571479e786eb95b2441c98cd25afc_115.png)

![](img/d02571479e786eb95b2441c98cd25afc_117.png)

![](img/d02571479e786eb95b2441c98cd25afc_118.png)

![](img/d02571479e786eb95b2441c98cd25afc_119.png)

本节课中，我们一起学习了如何从零开始实现用于大语言模型的强化学习。我们从加载模型和计算对数概率的基础开始，逐步实现了数据准备、策略损失计算和完整的训练循环。通过这个过程，我们深入理解了R1（Reinforcement Learning from Human Feedback）训练的核心机制，并构建了一个可扩展的实验代码库。希望这个教程能帮助你开始自己的RL for LLM研究之旅。