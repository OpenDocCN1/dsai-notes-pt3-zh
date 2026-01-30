# 📚 ShowMeAI 人工智能工具笔记教程

## 概述

在本教程中，我们将系统性地学习一系列人工智能、数据科学和编程工具的核心知识。课程内容涵盖了从基础的 Python 编程、数据处理，到高级的深度学习框架（如 PyTorch、TensorFlow、Transformers）的应用，以及数据可视化、数据库操作和办公软件高效技巧。本教程旨在为初学者提供一个清晰、全面的学习路径，帮助大家掌握现代 AI 开发所需的各项技能。

---

## 🧠 第一部分：深度学习与神经网络框架

上一节我们概述了本课程的整体结构，本节中我们将深入核心的深度学习框架。

### 课程 1：Transformers 原理细节及 NLP 任务应用 🔥

本课程深入讲解 Transformer 模型的架构原理及其在自然语言处理任务中的应用，并基于 Hugging Face 生态进行实践。

*   **L1.1 - 欢迎来到 Hugging Face 课程** 👋：介绍课程目标和 Hugging Face 生态系统。
*   **L1.2 - Hugging Face流水线功能** 🚀：学习使用 `pipeline` 函数快速进行 NLP 任务推理。
*   **L1.3 - 什么是迁移学习？** 🔄：解释迁移学习的概念及其在 NLP 中的重要性。
*   **L1.4 - Transformer架构** 🏗️：概述 Transformer 模型的核心设计思想。
*   **L1.5 - Transformer：编码器** 🔢：深入讲解 Transformer 编码器的结构和自注意力机制。其核心公式为 **Attention(Q, K, V) = softmax(QK^T / √d_k) V**。
*   **L1.6 - Transformer：解码器** 🔣：讲解 Transformer 解码器的结构及其与编码器的交互。
*   **L1.7 - Transformer：编码器-解码器** ⚙️：介绍完整的编码器-解码器架构，适用于序列到序列任务。
*   **L2.1 - 管道函数内部会发生什么？(PyTorch)** 🔍：剖析 `pipeline` 在 PyTorch 后端的具体执行步骤。
*   **L2.2 - 管道函数内部会发生什么？(TensorFlow)** 🔍：剖析 `pipeline` 在 TensorFlow 后端的具体执行步骤。
*   **L2.3 - 实例化 transformer 模型 (PyTorch)** 🧱：学习如何使用 PyTorch 加载和实例化预训练模型。示例代码：`model = AutoModel.from_pretrained(‘bert-base-uncased’)`。
*   **L2.4 - 实例化transformer模型(TensorFlow)** 🧱：学习如何使用 TensorFlow 加载和实例化预训练模型。
*   **L2.5 - Tokenizers 分词器概述** ✂️：介绍分词器的作用和主要类型。
*   **L2.6 - 基于词的分词器** 📝：讲解基于单词的分词方法及其优缺点。
*   **L2.7 - 基于字符的分词器** 🔤：讲解基于字符的分词方法及其应用场景。
*   **L2.8 - 基于子词的分词器** 🧩：讲解 BPE、WordPiece 等子词分词算法，这是现代 NLP 模型的标配。
*   **L2.9 - Tokenizer流水线处理** ⛓️：了解分词器从原始文本到模型 ID 的完整处理流程。
*   **L2.10 - 批处理输入(PyTorch)** 📦：学习如何将多个样本打包成批以提高 PyTorch 训练/推理效率。
*   **L2.11 - 批处理输入(TensorFlow)** 📦：学习 TensorFlow 下的批处理输入方法。
*   **L3.2 - 预处理句对数据(PyTorch)** 💬：处理像文本蕴含、相似度判断这样的句对任务数据。
*   **L3.3 - 什么是动态填充？** ⚡：解释动态填充技术，它能在批处理中智能地填充序列到相同长度。
*   **L3.4 - 训练器Trainer API** 🏋️：介绍 Hugging Face 提供的 `Trainer` 类，简化训练循环。
*   **L3.5 - 使用 PyTorch 编写训练流程** ⚙️：从零开始使用 PyTorch 编写完整的模型训练代码。
*   **L3.6 - 使用Accelerate增强您的PyTorch训练流程** 🚀：使用 `accelerate` 库简化分布式训练和混合精度训练。
*   **L4.1 - Hugging Face数据集概述(Tensorflow)** 📚：介绍 `datasets` 库及其与 TensorFlow 的集成。
*   **L4.2 - 预处理句对数据集(TensorFlow)** 💬：在 TensorFlow 中预处理句对数据。
*   **L4.3 - Keras介绍** 🧠：简要回顾 Keras API，作为 TensorFlow 的高级接口。
*   **L4.4 - 使用TensorFlow进行微调（迁移学习）** 🔧：在 TensorFlow 中实现模型的微调。
*   **L4.5 - 使用 TensorFlow 进行学习率调度** 📈：在 TensorFlow 训练中使用学习率调度策略。
*   **L4.6 - TensorFlow 预测和评估指标** 📊：使用 TensorFlow 模型进行预测并计算评估指标。
*   **L5.1 - 模型Hub中心速览** 🌐：浏览 Hugging Face Model Hub，发现和分享模型。
*   **L5.2 - 推送(模型)到hub API** 📤：学习如何将训练好的模型上传到 Hub。
*   **L5.3 - 在Model Hub管理模型repo** 🗂️：学习管理模型仓库，包括版本控制、README 编写等。
*   **L6.1 - Sylvain的在线直播讲解** 🎤：专家直播，深入探讨课程内容。
*   **L6.2 - Lewis 的在线直播讲解** 🎤：专家直播，答疑解惑。
*   **L6.3 - Sylvain的在线直播讲解** 🎤：专家直播，分享实战经验。
*   **L6.4 - Lewis的在线直播讲解** 🎤：专家直播，总结与展望。
*   **L6.5 - Omar的在线直播讲解** 🎤：专家直播，补充前沿知识。

### 课程 2：“当前最好的 TensorFlow 教程！” 🥇

这是一个全面的 TensorFlow 2.x 实战教程，从环境搭建到高级应用。

*   **L1 - 安装和设置深度学习环境(Anaconda 和 PyCharm)** 💻：详细指导如何搭建 TensorFlow 开发环境。
*   **L2 - 张量基础** 🔢：学习 TensorFlow 的核心数据结构——张量。
*   **L3 - 具有顺序和功能 API 的神经网络** 🧠：使用 Sequential 和 Functional API 构建神经网络。
*   **L4 - 具有顺序和功能 API 的卷积神经网络** 👁️：构建用于图像处理的 CNN 模型。
*   **L5 - 使用 L2 和 Dropout 添加正则化** 🛡️：学习防止模型过拟合的技术。L2正则化公式为 **Loss_new = Loss_original + λ * Σ(weights²)**。
*   **L6 - RNN、GRU、LSTM 和双向性** 🔄：讲解循环神经网络及其变体，用于序列数据。
*   **L7 - 函数式 API 的更深入示例** 🏗️：通过复杂例子（如多输入多输出模型）掌握 Functional API。
*   **L8 - 使用 Keras 进行模型子类化** 🎨：通过继承 `tf.keras.Model` 类实现高度自定义的模型。
*   **L9 - 自定义图层** 🧩：学习创建自定义的神经网络层。
*   **L10 - 保存和加载模型** 💾：掌握模型的持久化方法。
*   **L11 - 迁移学习、微调和 TensorFlow Hub** 🔄：利用预训练模型和 TensorFlow Hub 加速开发。
*   **L12 - TensorFlow 数据集** 📚：使用 `tensorflow-datasets` 加载标准数据集。
*   **L13 - 数据增强** 🖼️：通过对训练图像进行变换（旋转、裁剪等）来增加数据多样性。
*   **L14 - 使用 Keras 进行回调并编写自定义回调** ⏰：使用回调函数在训练过程中执行特定操作（如早停、记录日志）。
*   **L15 - 自定义模型与拟合** ⚙️：深入自定义训练过程。
*   **L16 - 自定义训练循环** 🔁：从零开始编写训练循环，实现更精细的控制。
*   **L17 - 完整的 TensorBoard 指南** 📊：使用 TensorBoard 可视化训练过程、模型图和嵌入。
*   **L18 - 图像的自定义数据集** 🗂️：创建和管理自己的图像数据集。
*   **L19 - 使用 TextLineDataset 自定义文本数据集** 📖：创建和管理自己的文本数据集。
*   **L20 - 皮肤癌分类项目** 🩺：一个完整的端到端图像分类项目实战。

### 课程 3：140分钟入门 PyTorch ⚡

一个快速高效的 PyTorch 入门指南，覆盖核心概念。

*   **L1 - PyTorch 简介** 👋：介绍 PyTorch 及其动态计算图特性。
*   **L2 - PyTorch 张量简介** 🔢：学习 PyTorch 的基础数据结构——张量。
*   **L3 - Autograd的基础知识** 🤖：理解 PyTorch 的自动微分引擎。
*   **L4 - 使用 PyTorch 构建模型** 🧱：使用 `torch.nn.Module` 构建神经网络。
*   **L5 - PyTorch TensorBoard 支持** 📊：将 PyTorch 训练日志可视化到 TensorBoard。
*   **L6 - 使用 PyTorch 进行训练** 🏋️：编写完整的训练和验证循环。
*   **L7 - 使用Captum进行模型理解** 🔍：使用 Captum 库进行模型可解释性分析。
*   **L8 - 使用PyTorch进行生产推理部署** 🚀：学习如何导出和部署 PyTorch 模型。

### 课程 4：PyTorch 极简实战教程！🎯

另一个从理论到实践的 PyTorch 系统教程，包含更多实战项目。

*   **L1 - 安装** 💻：PyTorch 环境安装。
*   **L2 - 张量基础** 🔢：张量操作。
*   **L3 - 使用 Autograd 计算梯度** 📈：自动微分实践。
*   **L4 - 反向传播 - 理论与实例** 🔙：深入讲解反向传播算法原理。
*   **L5 - 带有 Autograd 和反向传播的梯度下降** ⬇️：结合 Autograd 实现梯度下降。
*   **L6 - 训练管道：模型、损失和优化器** ⛓️：介绍训练的三个核心组件。
*   **L7 - 线性回归** 📉：第一个完整的回归模型实战。
*   **L8 - 逻辑回归** 🔮：第一个完整的分类模型实战。
*   **L9 - 数据集和数据加载器 - 批量训练** 📦：使用 `DataLoader` 高效加载数据。
*   **L10 - 数据集转换** 🛠️：数据预处理与增强。
*   **L11 - Softmax 和交叉熵** 🎲：多分类问题的损失函数。交叉熵公式为 **Loss = -Σ(y_i * log(ŷ_i))**。
*   **L12 - 激活函数** ⚡：讲解 ReLU, Sigmoid, Tanh 等激活函数。
*   **L13 - 前馈神经网络** 🧠：构建全连接神经网络。
*   **L14 - 卷积神经网络 (CNN)** 👁️：构建卷积神经网络处理图像。
*   **L15 - 迁移学习** 🔄：在 PyTorch 中应用迁移学习。
*   **L16 - 如何使用 TensorBoard** 📊：PyTorch 与 TensorBoard 集成。
*   **L17 - 保存和加载模型** 💾：模型持久化。
*   **L18 - 创建和部署深度学习应用程序** 🌐：使用 Flask 和 Heroku 部署模型。
*   **L19 - 使用循环神经网络进行名称分类** 🔤：RNN 实战项目。
*   **L20 - RNN & LSTM & GRU** 🔄：详细讲解各类循环神经网络单元。
*   **L21 - 调整学习率以获得更好的结果** 📶：学习率调度策略。
*   **L22 - PyTorch Lightning** ⚡：介绍这个简化 PyTorch 研究的框架。

### 课程 5：Pytorch 进阶学习讲座！🚀

针对已有 PyTorch 基础的学习者，探讨高级主题和生态工具。

*   **L1 - PyTorch 中的复数** 🧮：支持复数运算。
*   **L2 - 使 PyTorch 更加“与 NumPy 兼容”** 🔄：与 NumPy 的无缝交互。
*   **L3 - Autograd的高级API** 🛠️：高级自动微分技巧。
*   **L4 - PyTorch 分布式 RPC** 🗣️：远程过程调用，用于分布式训练。
*   **L5 - PyTorch 分布式数据并行 (DDP)** ⚡：数据并行分布式训练。
*   **L6 - TorchAudio** 🎵：音频处理库。
*   **L7 - TorchText** 📖：文本处理库。
*   **L8 - TorchVision** 👁️：图像处理与预训练模型库。
*   **L9 - 最新的Profiler API和最佳实践** 📋：性能分析与优化。
*   **L10 - 使用TensorBoard进行可视化** 📊：高级可视化技巧。
*   **L11 - PyTorch 性能** ⚡：性能调优。
*   **L12 - Windows上的PyTorch** 🪟：在 Windows 系统上的使用。
*   **L13 - PyTorch移动版** 📱：移动端部署。
*   **L14 - PyTorch 移动和 Android 神经网络 API** 🤖：与 Android NNAPI 集成。

### 课程 6：T81-558 ｜ 深度神经网络应用 📘

一个大学级别的深度学习应用课程，内容非常全面。

*   **讲座 - Python、Keras和TensorFlow深度学习课程以及深度神经网络的应用**：课程总览。
*   **L1.1 - 深度神经网络课程概述的应用**：课程目标与结构。
*   **L1.2 - 深度学习 Python 简介**：必备 Python 知识回顾。
*   **L1.3 - Python 列表、字典、集合和 JSON**：Python 数据结构。
*   **L1.4 - 深度学习的 Python 文件处理**：文件读写操作。
*   **L1.5 - Python 函数、Lambda 和 Map／Reduce**：函数式编程概念。
*   **讲座 - 在 Mac OSX M1 中安装 TensorFlow 2.5、Keras 和 Python 3.9**：M1芯片环境配置。
*   **讲座 - 使用 CONDA 安装 TensorFlow／Keras CPU／GPU版本**：Conda 环境管理。
*   **讲座 - 在Mac OSX中安装TensorFlow 2.4、Keras和Python 3.8**：macOS 环境配置。
*   **讲座 - 使用 Google CoLab 进行深度神经网络课程应用**：使用免费云端 GPU。
*   **讲座 - 如何提交深度学习应用的作业**：课程作业规范。
*   **L2.1 - 深度学习数据处理工具库Pandas 简介**：Pandas 基础。
*   **L2.2 - 使用Pandas为 Keras 编码类别型数据**：数据预处理。
*   **L2.3 - Python Pandas 中的数据分组、排序和改组**：数据操作。
*   **L2.4 - 在 Pandas 中为 Keras 使用 Apply 和 Map**：数据转换。
*   **L2.5 - 使用Pandas进行Keras深度学习的特征工程**：特征构建。
*   **L3.1 - Keras深度学习和神经网络编程介绍**：Keras 入门。
*   **L3.2 - 深度学习工具库TensorFlow和Keras简介**：TF & Keras 生态。
*   **L3.3 - 保存和加载Keras神经网络模型**：模型持久化。
*   **L3.4 - 在Keras中提前停止以防止过拟合**：早停法。
*   **L3.5 - 提取Keras权重并手动进行神经网络计算**：理解模型内部。
*   **L4.1 - 为Keras深度学习编码特征向量**：特征编码。
*   **L4.2 - Keras构建深度神经网络多类分类并用ROC和AUC评估**：多分类与评估。
*   **L4.3 - Keras深度神经网络回归建模与RMSE评估**：回归任务与评估。RMSE公式为 **√(Σ(ŷ_i - y_i)² / n)**。
*   **L4.4 - 反向传播、Nesterov动量和ADAM训练**：优化算法详解。
*   **L4.5 - 从头开始计算神经网络RMSE和对数损失**：手动实现损失计算。
*   **L5.1 - 正则化简介：Ridge 和 Lasso**：正则化理论。
*   **L5.2 - 在Keras中使用K折交叉验证**：交叉验证实践。
*   **L5.3 - 在Keras中使用L1和L2正则化来减少过拟合**：在模型中添加正则化。
*   **L5.4 - Keras使用Dropout以减少过拟合**：Dropout 技术。
*   **L5.5 - bootstrapping与基准超参数**：自助法与超参数基准。
*   **L6.1 - 基于Keras神经网络建模需要的图像处理**：图像预处理。
*   **L6.2 - 用于MNIST和fashion-MNIST的Keras卷积神经网络**：CNN 实战。
*   **L6.3 - 在 Keras 中实现 ResNet**：实现残