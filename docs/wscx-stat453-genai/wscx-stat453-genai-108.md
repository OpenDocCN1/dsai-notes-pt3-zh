# 108：L13.9.2 - 在 PyTorch 中保存和加载模型 📚

在本节课中，我们将要学习如何在 PyTorch 中保存和加载训练好的模型。这对于中断后继续训练、模型部署或分享模型至关重要。

上一节我们介绍了模型训练的基本流程，本节中我们来看看如何将训练成果持久化保存。

![](img/5a3e0422b6af2773919fc4e6fa067d70_1.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_3.png)

## 准备工作与模型训练 🛠️

首先，我们需要设置环境并训练一个简单的模型。以下代码展示了如何导入必要的库并添加自定义辅助文件的路径。

```python
import sys
sys.path.insert(0, ‘..‘) # 返回上一级目录以找到辅助文件
```

接着，我们导入所有必要的模块并初始化模型、数据加载器等组件。这个过程与之前的训练流程完全一致。

![](img/5a3e0422b6af2773919fc4e6fa067d70_5.png)

```python
# 假设 helper 模块包含了模型定义、数据准备等函数
from helper import *
model, train_loader, val_loader, optimizer, scheduler = initialize_training()
```

![](img/5a3e0422b6af2773919fc4e6fa067d70_7.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_8.png)

为了演示，我们只训练模型两个周期。

![](img/5a3e0422b6af2773919fc4e6fa067d70_10.png)

```python
num_epochs = 2
train_model(model, train_loader, val_loader, optimizer, scheduler, num_epochs)
```

![](img/5a3e0422b6af2773919fc4e6fa067d70_12.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_14.png)

训练完成后，我们可以使用一个辅助函数来可视化一些预测结果，以检查模型表现。

![](img/5a3e0422b6af2773919fc4e6fa067d70_16.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_18.png)

```python
show_examples(model, val_loader)
```

![](img/5a3e0422b6af2773919fc4e6fa067d70_20.png)

此外，我们还可以计算混淆矩阵来更详细地分析模型的错误类型。混淆矩阵显示了预测标签与真实标签的对比情况。

![](img/5a3e0422b6af2773919fc4e6fa067d70_22.png)

以下是混淆矩阵能帮助我们理解的信息：
*   理想情况下，最高的数值应出现在矩阵的对角线上。
*   通过观察非对角线的高值，我们可以发现模型最容易混淆哪些类别（例如，将数字9误判为5，或将2误判为7）。

## 保存模型状态 💾

模型训练完成后，下一步就是保存其状态，以便后续使用。在 PyTorch 中，这主要通过保存模型的参数（即状态字典）来实现。

![](img/5a3e0422b6af2773919fc4e6fa067d70_24.png)

核心的保存操作涉及以下三个部分：

```python
# 保存模型参数
torch.save(model.state_dict(), ‘model.pt‘)
# 保存优化器状态（例如 SGD 中的动量）
torch.save(optimizer.state_dict(), ‘optimizer.pt‘)
# 保存学习率调度器状态
torch.save(scheduler.state_dict(), ‘scheduler.pt‘)
```

![](img/5a3e0422b6af2773919fc4e6fa067d70_26.png)

*   `model.state_dict()`：是一个 Python 字典对象，包含了模型的所有可学习参数（权重和偏置）。
*   文件扩展名 `.pt` 或 `.pth` 是 PyTorch 的常见约定，但你可以使用任何名称。
*   保存优化器和调度器状态是可选的，但如果你想从中断处**精确恢复训练**，则必须保存它们。

执行上述代码后，你会在指定文件夹中找到这些 `.pt` 文件。

## 加载模型并继续训练 🔄

现在，假设我们想要加载已保存的模型并继续训练，或者在新环境中使用它。首先，我们需要在一个新的脚本或笔记本中重新初始化模型结构。

![](img/5a3e0422b6af2773919fc4e6fa067d70_28.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_29.png)

加载模型的过程分为几个关键步骤：

1.  **重新初始化模型**：必须创建与保存时结构完全相同的模型类实例。
2.  **加载参数**：将保存的状态字典加载到初始化好的模型中。
3.  **加载优化器和调度器**（可选）：如果打算继续训练，也需要加载它们的状态。

![](img/5a3e0422b6af2773919fc4e6fa067d70_31.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_32.png)

以下是实现代码：

![](img/5a3e0422b6af2773919fc4e6fa067d70_34.png)

```python
# 1. 重新初始化模型结构
model = MyModelClass() # 使用与保存时相同的模型类
optimizer = torch.optim.SGD(model.parameters(), lr=0.01, momentum=0.9)
scheduler = torch.optim.lr_scheduler.StepLR(optimizer, step_size=30)

![](img/5a3e0422b6af2773919fc4e6fa067d70_36.png)

# 2. 加载保存的状态
model.load_state_dict(torch.load(‘model.pt‘))
optimizer.load_state_dict(torch.load(‘optimizer.pt‘))
scheduler.load_state_dict(torch.load(‘scheduler.pt‘))

# 3. 将模型设置为评估或训练模式
model.eval() # 用于推理/测试
# 或者 model.train() # 用于继续训练
```

![](img/5a3e0422b6af2773919fc4e6fa067d70_38.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_39.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_40.png)

**重要提示**：必须在加载 `state_dict` 之前实例化模型、优化器和调度器，因为 `load_state_dict` 方法是将参数填充到一个已存在的对象中，而不是创建对象本身。

![](img/5a3e0422b6af2773919fc4e6fa067d70_41.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_43.png)

完成加载后，你就可以继续训练模型了。

![](img/5a3e0422b6af2773919fc4e6fa067d70_45.png)

```python
# 继续训练更多周期
train_model(model, train_loader, val_loader, optimizer, scheduler, num_epochs=10)
```

![](img/5a3e0422b6af2773919fc4e6fa067d70_46.png)

![](img/5a3e0422b6af2773919fc4e6fa067d70_48.png)

本节课中我们一起学习了 PyTorch 中保存和加载模型的核心方法。我们了解了如何保存模型的 `state_dict` 以及优化器和调度器的状态，并掌握了如何重新初始化模型结构并加载这些状态以继续训练或进行预测。下一节，我们将把注意力转向经典的 AlexNet 模型。