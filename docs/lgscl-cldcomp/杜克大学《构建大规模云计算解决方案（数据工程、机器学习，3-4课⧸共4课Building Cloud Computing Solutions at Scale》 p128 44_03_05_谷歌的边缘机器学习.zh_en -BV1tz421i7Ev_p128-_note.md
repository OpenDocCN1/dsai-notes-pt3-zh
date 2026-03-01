# 构建大规模云计算解决方案（数据工程、机器学习）：3-4课：谷歌的边缘机器学习 🧠

![](img/00eb09c89e9cead813efa69c14465817_0.png)

在本节课中，我们将学习如何在谷歌云平台（GCP）的生态系统中，将云端训练的机器学习模型部署到边缘设备上。我们将重点介绍几种主流的工作流程，包括使用TensorFlow Lite、Core ML以及Coral USB加速器，并通过一个具体的演示，展示如何将预训练模型部署到Coral设备并进行推理。

## 概述

上一节我们讨论了边缘计算的基本概念。本节中，我们来看看谷歌为边缘机器学习提供的具体工具和工作流程。核心思路是：在云端（如使用Google AutoML Vision）训练模型，然后将其导出为适用于边缘设备的格式，最终在设备上运行推理。

## 谷歌生态系统工作流程

最常见的“黄金路径”或最简单的工作流程如下：

1.  **使用AutoML Vision训练模型**：在GCP控制台中，进入AutoML Vision服务。上传你的数据集（例如花卉数据集），然后开始训练模型。
2.  **选择移动端优化模型**：在训练模型时，关键步骤是选择基于移动设备的模型架构。在训练设置中，选择“Edge”选项，以便下载模型供离线使用。
3.  **权衡模型性能**：在继续之前，你需要决定是优先考虑最高精度还是最快预测速度。模型越小，延迟越低，这对于实时应用（如车辆物体检测）可能至关重要。而对于非实时任务（如手写识别），则可以选择精度更高的模型。

训练完成后，你可以在“测试与使用”部分下载模型。对于学生而言，最容易上手的工作流程通常涉及以下三种格式：

以下是三种主要的边缘部署格式：

*   **TensorFlow Lite (TFLite)**：适用于Android等设备的轻量级格式。
*   **Core ML**：苹果设备的原生格式，可直接从Google AutoML导出。
*   **Coral**：谷歌专为边缘AI设计的硬件平台及其模型格式。

![](img/00eb09c89e9cead813efa69c14465817_2.png)

![](img/00eb09c89e9cead813efa69c14465817_3.png)

![](img/00eb09c89e9cead813efa69c14465817_5.png)

## TensorFlow Lite 工作流程

![](img/00eb09c89e9cead813efa69c14465817_7.png)

现在，让我们简要看一下TensorFlow Lite工作流程。其核心思想非常简单：

**在云端训练模型 -> 下载 `.tflite` 模型文件 -> 在设备上替换并运行。**

![](img/00eb09c89e9cead813efa69c14465817_9.png)

具体到项目中，你会获得一个 `labels.txt` 文件和一个 `graph.lite`（或 `.tflite`）文件。你只需要用自己训练的模型文件替换掉示例项目中的对应文件即可。

我们可以将支持的设备分类如下：

以下是支持的不同设备和对应工作流程：

*   **Android设备 (来自 TFLite)**：使用导出的 `.tflite` 模型。
*   **iOS/Mac设备 (来自 Google AutoML)**：选择导出为Core ML格式。谷歌会直接将模型导出为Core ML格式，然后你可以在苹果设备上使用它。
*   **Coral AI设备**：这是我们将要重点演示的选项。
*   **其他计算机视觉设备和工作流程**：例如容器部署等，但相关性较低。

## Coral USB加速器实战演示 🚀

Coral提供了一种非常直接的工作流程。你可以直接从AutoML导出模型，获得 `.tflite` 文件并下载。接下来，我将逐步演示如何使用Coral USB加速器。

我将切换到实际操作，展示从设置加速器到运行推理的完整流程。我会将浏览器和终端并排显示，以便观察。

### 步骤1：安装Edge TPU运行时

首先，我们需要按照官方文档安装Edge TPU运行时。对于macOS系统，建议使用Homebrew。

在终端中，进入一个工作目录（例如 `~/src`），然后运行以下命令下载并安装运行时：

```bash
# 进入工作目录
cd ~/src
# 下载运行时包
curl -LO https://github.com/google-coral/libedgetpu/releases/download/release-grouper/edgetpu_runtime_20240126.zip
# 解压文件
unzip edgetpu_runtime_20240126.zip
# 进入解压后的目录并安装
cd edgetpu_runtime
sudo bash install.sh
```

安装过程中，系统可能会询问是否让设备以最高性能（可能更热）运行，对于实验目的，可以选择“是”。安装脚本会自动安装所需的库。

### 步骤2：连接硬件并设置Python环境

接下来，用提供的USB线将Coral USB加速器连接到电脑。

然后，我们需要安装TensorFlow Lite库。为了避免污染系统Python环境，最佳实践是先创建一个虚拟环境。

![](img/00eb09c89e9cead813efa69c14465817_11.png)

以下是创建和激活虚拟环境的步骤：

```bash
# 创建名为‘tpu_demo’的虚拟环境
python3 -m venv ~/.tpu_demo
# 激活虚拟环境
source ~/.tpu_demo/bin/activate
```

![](img/00eb09c89e9cead813efa69c14465817_13.png)

![](img/00eb09c89e9cead813efa69c14465817_15.png)

激活虚拟环境后，终端提示符通常会变化。接着，我们创建一个工作目录并克隆包含示例模型和代码的仓库。

```bash
# 创建并进入工作目录
mkdir coral && cd coral
# 克隆示例仓库
git clone https://github.com/google-coral/tflite.git
```

### 步骤3：安装依赖并运行示例

进入Python示例目录，并运行安装脚本以安装必要的Python包。

```bash
# 进入示例目录
cd tflite/python/examples/classification
# 安装依赖（通常通过requirements.txt或setup.py）
bash install_requirements.sh  # 具体脚本名可能不同，请参考仓库说明
```

![](img/00eb09c89e9cead813efa69c14465817_17.png)

在运行任何代码前，最好先查看一下脚本内容。我们可以用 `vim` 或 `cat` 查看 `classify_image.py` 脚本。它会加载标签文件、初始化TFLite解释器（该解释器会与Edge TPU硬件通信），然后解析参数并输出预测结果。这是一个很好的示例，你可以修改它以适应自己的需求。

![](img/00eb09c89e9cead813efa69c14465817_19.png)

![](img/00eb09c89e9cead813efa69c14465817_21.png)

查看完毕后，我们可以运行提供的示例，对一张鹦鹉图片进行分类。

```bash
# 运行示例分类脚本（具体命令参考仓库README）
python3 classify_image.py \
  --model models/mobilenet_v2_1.0_224_inat_bird_quant_edgetpu.tflite \
  --labels models/inat_bird_labels.txt \
  --input images/parrot.jpg
```

![](img/00eb09c89e9cead813efa69c14465817_23.png)

如果一切设置正确，脚本将输出预测结果，例如“猩猩金刚鹦鹉”，并给出77%的置信度。

![](img/00eb09c89e9cead813efa69c14465817_25.png)

![](img/00eb09c89e9cead813efa69c14465817_27.png)

### 步骤4：深入探索与自定义

![](img/00eb09c89e9cead813efa69c14465817_29.png)

![](img/00eb09c89e9cead813efa69c14465817_31.png)

我们可以进一步探索。在 `models` 目录下，有使用的模型文件和 `inat_bird_labels.txt` 标签文件。查看标签文件，可以看到它能识别许多种鸟类。

![](img/00eb09c89e9cead813efa69c14465817_33.png)

为了更深入地理解系统如何工作，我们可以从网上下载一张标签列表中鸟类的图片（例如“美洲崖燕”）进行测试。

![](img/00eb09c89e9cead813efa69c14465817_35.png)

1.  从维基百科下载美洲崖燕的图片，保存到桌面。
2.  将图片移动到示例的 `images` 目录下，并重命名为简单的名称（如 `cliff_swallow.jpg`）。
3.  修改运行命令，指定新的图片路径和对应的标签文件，再次运行分类脚本。

![](img/00eb09c89e9cead813efa69c14465817_37.png)

```bash
python3 classify_image.py \
  --model models/mobilenet_v2_1.0_224_inat_bird_quant_edgetpu.tflite \
  --labels models/inat_bird_labels.txt \
  --input images/cliff_swallow.jpg
```

脚本成功预测出“崖燕”，置信度为82%。这展示了Coral Edge TPU芯片强大的本地推理能力。

![](img/00eb09c89e9cead813efa69c14465817_39.png)

![](img/00eb09c89e9cead813efa69c14465817_41.png)

### 步骤5：使用其他预训练模型

更强大的是，我们不仅可以使用AutoML训练的模型，还可以使用来自TensorFlow Hub等社区的预训练模型。

![](img/00eb09c89e9cead813efa69c14465817_43.png)

![](img/00eb09c89e9cead813efa69c14465817_45.png)

![](img/00eb09c89e9cead813efa69c14465817_47.png)

1.  访问TensorFlow Hub或Coral官方模型库。
2.  找到一个预训练模型（例如，一个植物分类模型或通用的MobileNet模型），并下载其TFLite格式文件（注意选择适用于Coral Edge TPU的量化版本）。
3.  同时下载或创建对应的标签文件。
4.  将下载的 `.tflite` 模型文件和 `labels.txt` 文件放入项目的 `models` 目录。
5.  找一张符合模型分类范畴的测试图片（例如，从网上下载一张“虎鲨”的图片，放入 `images` 目录）。
6.  修改运行命令，指向新的模型、标签和输入图片。

![](img/00eb09c89e9cead813efa69c14465817_49.png)

![](img/00eb09c89e9cead813efa69c14465817_51.png)

![](img/00eb09c89e9cead813efa69c14465817_53.png)

```bash
python3 classify_image.py \
  --model models/mobilenet_ssd_v2_coco_quant_postprocess_edgetpu.tflite \
  --labels models/imagenet_labels.txt \
  --input images/tiger_shark.jpg
```

运行后，模型以99%的置信度成功识别出“虎鲨”。

## 总结

![](img/00eb09c89e9cead813efa69c14465817_55.png)

本节课中，我们一起学习了谷歌边缘机器学习的核心工作流程。我们了解了如何通过Google AutoML Vision在云端训练模型，并导出为TFLite、Core ML等边缘格式。随后，我们通过一个详细的实战演示，掌握了如何设置和使用Coral USB加速器这一强大的边缘AI硬件，包括安装运行时、配置Python环境、运行示例代码，以及最关键的一步——**加载自定义或社区预训练的模型进行本地推理**。

![](img/00eb09c89e9cead813efa69c14465817_57.png)

![](img/00eb09c89e9cead813efa69c14465817_58.png)

这套流程的威力在于其灵活性：你既可以使用自己定制的模型，也可以利用庞大的开源模型库，在拥有专用TPU的边缘设备上实现低延迟、高效率的智能识别。随着社区的发展，适用于边缘设备的模型将会越来越丰富。