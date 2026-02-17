# Hugging Face中的量化基础：P4：按数据类型加载模型

在本节课中，我们将学习如何使用不同的数据类型（如 `float16` 或 `bfloat16`）加载机器学习模型，并研究它们对模型性能和内存占用的影响。

## 概述：模型数据类型与精度

模型的数据类型指的是其权重参数的存储精度。每个权重参数都是一个可学习的矩阵，可以用不同的精度表示，例如32位（`float32`）、16位（`float16` 或 `bfloat16`）。检查模型的数据类型就是检查其权重的数据类型。

**公式**：模型权重矩阵 `W` 的精度可以是 `float32`、`float16` 或 `bfloat16`。

## 检查模型的数据类型

![](img/eb8b5b1a408d3f5cd170452eca1d6221_1.png)

上一节我们介绍了模型数据类型的含义，本节中我们来看看如何实际检查一个PyTorch模型的数据类型。

我们将使用一个虚拟的小型Transformer模型作为示例。

```python
# 导入虚拟模型架构
from helpers import DummyModel

# 加载模型
model = DummyModel()
print(model)
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_3.png)

为了检查模型参数的数据类型，我们可以使用PyTorch的 `named_parameters()` 方法。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_5.png)

以下是检查模型参数数据类型的步骤：

![](img/eb8b5b1a408d3f5cd170452eca1d6221_7.png)

1.  遍历模型的命名参数。
2.  打印每个参数的名称和其数据类型（`dtype`）。

```python
def print_param_dtype(model):
    for name, param in model.named_parameters():
        print(f"{name}: {param.dtype}")

# 打印默认加载模型的数据类型
print_param_dtype(model)
```

运行上述代码后，你会发现所有模型权重默认都以 `float32` 精度加载。

## 转换模型的数据类型

了解了如何检查数据类型后，我们来看看如何将模型转换为不同的精度，例如 `float16` 或 `bfloat16`。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_9.png)

在PyTorch中，转换模型数据类型非常简单。假设目标数据类型是 `float16`，你可以使用以下任一方法：

*   `model.to(torch.float16)`
*   `model.half()` （专用于转换为 `float16`）
*   `model.bfloat16()` （专用于转换为 `bfloat16`）

让我们尝试将模型转换为 `float16`：

```python
import torch

![](img/eb8b5b1a408d3f5cd170452eca1d6221_11.png)

# 将模型转换为 float16
model_fp16 = model.half()
print_param_dtype(model_fp16)
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_13.png)

现在，所有模型权重都已成功转换为 `float16`。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_15.png)

## 不同精度下的模型推理

![](img/eb8b5b1a408d3f5cd170452eca1d6221_17.png)

转换精度后，我们需要测试模型是否仍能正常工作。我们将使用一个虚拟输入进行推理测试。

首先，我们使用原始的 `float32` 模型进行推理：

![](img/eb8b5b1a408d3f5cd170452eca1d6221_19.png)

```python
# 创建一个虚拟输入（假设是token IDs）
input_ids = torch.LongTensor([[1, 2, 3, 4]])
# 使用 float32 模型推理
logits_fp32 = model(input_ids)
print(logits_fp32)
```

接下来，我们尝试使用 `float16` 模型在CPU上进行推理：

![](img/eb8b5b1a408d3f5cd170452eca1d6221_21.png)

```python
# 使用 float16 模型推理（在CPU上可能会失败）
try:
    logits_fp16 = model_fp16(input_ids)
except Exception as e:
    print(f"推理失败，错误信息: {e}")
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_23.png)

你会发现，在CPU上使用 `float16` 进行推理可能会失败，因为许多CPU内核不支持 `float16` 运算。

为了解决这个问题，我们可以尝试使用 `bfloat16` 精度，它在CPU上通常有更好的支持。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_25.png)

```python
# 创建模型副本并转换为 bfloat16
model_bf16 = DummyModel()
model_bf16.load_state_dict(model.state_dict()) # 复制权重
model_bf16 = model_bf16.bfloat16()
print_param_dtype(model_bf16)

# 使用 bfloat16 模型推理
logits_bf16 = model_bf16(input_ids)
print(logits_bf16)
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_27.png)

为了比较精度转换带来的影响，我们可以计算 `float32` 模型和 `bfloat16` 模型输出之间的差异：

```python
# 计算平均绝对误差
mean_error = torch.mean(torch.abs(logits_fp32 - logits_bf16))
print(f"FP32 与 BF16 模型输出的平均绝对误差: {mean_error.item()}")
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_29.png)

通常，从 `float32` 转换到 `bfloat16` 只会带来微小的数值差异，在大多数情况下不会导致模型性能显著下降。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_31.png)

## 加载真实生成式模型并比较性能

在掌握了基础操作后，让我们将所学应用于一个真实的生成式AI模型，并研究不同精度对其实用性能的影响。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_33.png)

我们将加载一个多模态的BLIP模型，它能够根据图像生成描述文字（图像字幕）。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_35.png)

首先，我们以默认的 `float32` 精度加载模型：

```python
from transformers import BlipForConditionalGeneration

# 以默认 float32 精度加载模型
model_name = "Salesforce/blip-image-captioning-base"
model_fp32 = BlipForConditionalGeneration.from_pretrained(model_name)

# 检查模型数据类型和内存占用
print_param_dtype(model_fp32)
print(f"FP32 模型内存占用: {model_fp32.get_memory_footprint() / 1024**2:.2f} MB")
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_37.png)

接下来，我们直接在加载时指定 `bfloat16` 精度。这是Hugging Face Transformers库推荐的做法。

```python
# 直接在加载时指定 bfloat16 精度
model_bf16 = BlipForConditionalGeneration.from_pretrained(model_name, torch_dtype=torch.bfloat16)

![](img/eb8b5b1a408d3f5cd170452eca1d6221_39.png)

# 检查内存占用
mem_fp32 = model_fp32.get_memory_footprint()
mem_bf16 = model_bf16.get_memory_footprint()
print(f"BF16 模型内存占用: {mem_bf16 / 1024**2:.2f} MB")
print(f"内存减少比例: {(1 - mem_bf16/mem_fp32)*100:.1f}%")
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_41.png)

可以看到，使用 `bfloat16` 精度可以将模型内存占用减少大约一半。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_43.png)

现在，我们通过实际的图像字幕生成任务，定性地比较两个模型的输出是否相似。

```python
from transformers import BlipProcessor
from PIL import Image
import requests

![](img/eb8b5b1a408d3f5cd170452eca1d6221_45.png)

# 加载处理器和示例图片
processor = BlipProcessor.from_pretrained(model_name)
url = "http://images.cocodataset.org/val2017/000000039769.jpg"
image = Image.open(requests.get(url, stream=True).raw)
image.show() # 显示图片

![](img/eb8b5b1a408d3f5cd170452eca1d6221_47.png)

# 定义生成辅助函数
def generate_caption(processor, image, model):
    inputs = processor(image, return_tensors="pt")
    out = model.generate(**inputs, max_new_tokens=20)
    caption = processor.decode(out[0], skip_special_tokens=True)
    return caption

# 使用 FP32 模型生成字幕
caption_fp32 = generate_caption(processor, image, model_fp32)
print(f"FP32 模型生成: {caption_fp32}")

![](img/eb8b5b1a408d3f5cd170452eca1d6221_49.png)

# 使用 BF16 模型生成字幕
caption_bf16 = generate_caption(processor, image, model_bf16)
print(f"BF16 模型生成: {caption_bf16}")
```

![](img/eb8b5b1a408d3f5cd170452eca1d6221_51.png)

两个模型生成的描述会非常接近（例如“a woman sitting on the beach with her dog”和“a woman sitting on the beach with a dog”）。微小的差异源于层与层之间累积的数值误差，但整体性能保持一致。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_53.png)

## 高级技巧：直接初始化目标精度模型

在之前的工作流程中，我们通常是先加载 `float32` 模型，再转换精度。但在生产环境中，为了节省内存，我们可能希望直接以目标精度初始化模型。

Transformers库在幕后使用了PyTorch的 `torch.set_default_dtype()` 方法来实现这一点。我们可以手动模拟这个过程：

```python
# 1. 设置默认张量数据类型为 bfloat16
torch.set_default_dtype(torch.bfloat16)

# 2. 此时初始化的模型张量将默认为 bfloat16
model_direct_bf16 = BlipForConditionalGeneration.from_pretrained(model_name)
print_param_dtype(model_direct_bf16) # 权重应为 bfloat16

# 3. （重要）将默认 dtype 重置回 float32，避免影响后续其他代码
torch.set_default_dtype(torch.float32)
```

**注意**：使用此方法后，务必重置默认数据类型，以免影响项目中其他部分的张量创建。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_55.png)

## 总结

本节课中我们一起学习了：

![](img/eb8b5b1a408d3f5cd170452eca1d6221_57.png)

1.  **模型数据类型的概念**：即模型权重参数的存储精度（如 `float32`, `float16`, `bfloat16`）。
2.  **检查与转换数据类型**：使用 `model.named_parameters()` 检查，使用 `model.to(dtype)`、`.half()` 或 `.bfloat16()` 进行转换。
3.  **不同精度下的推理**：`float16` 在CPU上可能不受支持，而 `bfloat16` 通常是CPU上半精度推理的更好选择，且精度损失很小。
4.  **加载真实模型**：使用 `from_pretrained(..., torch_dtype=...)` 参数直接加载指定精度的模型，可以显著减少内存占用（约50%）。
5.  **直接初始化目标精度模型**：通过 `torch.set_default_dtype()` 可以直接初始化目标精度的模型，优化内存使用流程。

你可以尝试将这些技巧应用于Hugging Face Hub上的其他模型（如音频、视觉模型），并观察不同精度带来的影响。

![](img/eb8b5b1a408d3f5cd170452eca1d6221_59.png)

在下一课中，您将学习如何使用Hugging Face的Quanto库，通过量化将模型加载为 `int8` 精度。