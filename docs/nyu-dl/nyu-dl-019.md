# 19：19. 第10周 – 实践：卡车倒车入库 🚛

![](img/7e912af13be2d5ea35ea005d087a22be_1.png)

![](img/7e912af13be2d5ea35ea005d087a22be_3.png)

在本节课中，我们将学习如何设计一个非线性控制器，通过自我学习的方式，控制一辆带有拖车的卡车从任意初始位置倒车进入装卸码头。这是一个经典的、具有挑战性的控制问题，我们将通过训练神经网络来解决它。

---

## 概述与目标

![](img/7e912af13be2d5ea35ea005d087a22be_5.png)

![](img/7e912af13be2d5ea35ea005d087a22be_7.png)

我们的目标是：给定卡车和拖车的初始位置（包括坐标和角度），训练一个神经网络控制器，使其能够输出一系列方向盘转向角，引导卡车倒车，直到拖车的尾部与码头平行并紧贴码头。

![](img/7e912af13be2d5ea35ea005d087a22be_9.png)

![](img/7e912af13be2d5ea35ea005d087a22be_11.png)

![](img/7e912af13be2d5ea35ea005d087a22be_13.png)

**核心状态变量**：
卡车和拖车的状态可以用6个变量描述：
*   **卡车角度** `θ_cab`：卡车相对于x轴的角度。
*   **卡车铰接点坐标** `(x_cab, y_cab)`：卡车后部与拖车连接处的坐标。
*   **拖车尾部坐标** `(x_trailer, y_trailer)`：拖车尾部的坐标。
*   **拖车角度** `θ_trailer`：拖车相对于x轴的角度。

**最终目标状态**：
1.  拖车尾部坐标 `(x_trailer, y_trailer)` 应尽可能接近码头坐标 `(x_dock, y_dock)`。
2.  拖车角度 `θ_trailer` 应为0，即拖车与码头平行（正交）。

---

## 系统动力学与挑战

上一节我们介绍了问题的目标，本节中我们来看看系统的运动学模型以及控制它的难点。

![](img/7e912af13be2d5ea35ea005d087a22be_15.png)

卡车-拖车系统的运动是高度非线性的。当我们尝试倒车时，微小的转向角变化可能导致拖车产生复杂、难以预测的摆动。手动设计一个能处理所有可能初始位置的控制律非常困难。

**运动学模型（简化表示）**：
系统的下一个状态 `s_{k+1}` 取决于当前状态 `s_k` 和当前转向角 `φ_k`。这可以用一个函数 `F` 来描述：
`s_{k+1} = F(s_k, φ_k)`
其中，`s_k = [x_cab, y_cab, θ_cab, x_trailer, y_trailer, θ_trailer]`， `φ_k` 是方向盘的转向角。

---

## 解决方案架构：双网络训练法

![](img/7e912af13be2d5ea35ea005d087a22be_17.png)

![](img/7e912af13be2d5ea35ea005d087a22be_19.png)

面对非线性控制难题，论文提出了一种分两阶段训练神经网络的解决方案。

### 第一阶段：训练模拟器网络 🧠

![](img/7e912af13be2d5ea35ea005d087a22be_21.png)

首先，我们需要一个能准确预测系统动力学的模型。即使我们有解析的运动学方程，训练一个“模拟器”网络也更具通用性。这对于那些没有精确数学模型、只有观测数据的复杂系统（如交通流中的车辆）尤其重要。

![](img/7e912af13be2d5ea35ea005d087a22be_23.png)

![](img/7e912af13be2d5ea35ea005d087a22be_25.png)

**训练方法**：
我们让卡车在随机初始状态和随机转向角下运行，收集大量的 `(当前状态, 转向角) -> 下一状态` 数据对。然后，我们训练一个神经网络来拟合这个映射关系。

![](img/7e912af13be2d5ea35ea005d087a22be_27.png)

![](img/7e912af13be2d5ea35ea005d087a22be_29.png)

![](img/7e912af13be2d5ea35ea005d087a22be_31.png)

以下是训练模拟器的核心步骤：

![](img/7e912af13be2d5ea35ea005d087a22be_33.png)

![](img/7e912af13be2d5ea35ea005d087a22be_35.png)

1.  **生成数据**：随机初始化卡车状态，并施加随机转向角，根据真实运动学方程计算下一状态，形成数据对 `(s_k, φ_k) -> s_{k+1}`。
2.  **构建网络**：输入是7维（6维状态 + 1维转向角），经过隐藏层（如45个单元），输出是6维的预测下一状态。
3.  **定义损失**：使用均方误差（MSE）损失函数，最小化预测状态与真实下一状态之间的差异。
    `Loss = MSE(s_{k+1}^{predicted}, s_{k+1}^{true})`
4.  **训练**：通过反向传播更新模拟器网络的权重，直到其能准确预测系统动态。

![](img/7e912af13be2d5ea35ea005d087a22be_37.png)

![](img/7e912af13be2d5ea35ea005d087a22be_39.png)

![](img/7e912af13be2d5ea35ea005d087a22be_41.png)

![](img/7e912af13be2d5ea35ea005d087a22be_43.png)

### 第二阶段：训练控制器网络 🎮

![](img/7e912af13be2d5ea35ea005d087a22be_45.png)

在拥有一个训练好的、可微分的模拟器网络后，我们就可以训练控制器网络了。控制器的任务是：观察当前状态，输出一个转向角。

**训练方法（时间展开与反向传播）**：
我们将控制器网络和固定权重的模拟器网络连接起来，形成一个“展开”的计算图。

1.  **前向传播**：从一个随机初始状态 `s_0` 开始。
    *   控制器 `C` 根据 `s_0` 输出转向角 `φ_0`。
    *   模拟器 `T` 根据 `(s_0, φ_0)` 预测下一状态 `s_1`。
    *   将 `s_1` 输入控制器 `C`，得到 `φ_1`，再输入模拟器 `T` 得到 `s_2`。
    *   重复此过程，直到满足终止条件（如撞到边界、达到最大步数或成功倒车入库），得到一条状态轨迹 `s_0, s_1, ..., s_K`。
2.  **计算最终损失**：损失函数基于轨迹的最终状态 `s_K`。
    *   我们希望 `(x_trailer_K, y_trailer_K)` 接近 `(x_dock, y_dock)`。
    *   我们希望 `θ_trailer_K` 接近 0。
    *   损失函数 `L_final` 可以定义为这些差异的加权和。
3.  **反向传播**：计算 `L_final` 相对于控制器网络参数 `θ_C` 的梯度。由于模拟器网络 `T` 是固定的且可微，梯度可以通过整个展开的计算图（从 `s_K` 一直回溯到 `s_0`）进行反向传播。这实质上是**随时间反向传播（BPTT）**的一种形式。
4.  **更新控制器**：使用计算出的梯度更新控制器网络的权重 `θ_C`，使其输出的转向角序列能引导系统到达期望的最终状态。

**关键点**：控制器网络的深度是可变的，它取决于每次模拟运行的步数 `K`。我们是在用一个**固定目标**（最终状态）来训练一个处理**可变长度输入序列**的网络。

---

## 实践演示与代码要点

让我们回到实践环节，看看代码中如何实现这些概念。

![](img/7e912af13be2d5ea35ea005d087a22be_47.png)

![](img/7e912af13be2d5ea35ea005d087a22be_49.png)

![](img/7e912af13be2d5ea35ea005d087a22be_51.png)

![](img/7e912af13be2d5ea35ea005d087a22be_53.png)

![](img/7e912af13be2d5ea35ea005d087a22be_55.png)

### 1. 环境设置与交互

![](img/7e912af13be2d5ea35ea005d087a22be_57.png)

![](img/7e912af13be2d5ea35ea005d087a22be_59.png)

首先，我们初始化一个卡车-拖车模拟环境。你可以手动输入转向角（-45度到+45度之间），并观察卡车如何运动，直观感受控制的难度。

![](img/7e912af13be2d5ea35ea005d087a22be_61.png)

![](img/7e912af13be2d5ea35ea005d087a22be_63.png)

![](img/7e912af13be2d5ea35ea005d087a22be_65.png)

![](img/7e912af13be2d5ea35ea005d087a22be_67.png)

```python
# 伪代码示例：初始化并单步模拟
env = TruckTrailerEnv()
state = env.reset() # 获取初始状态 s0
steering_angle = 15 # 手动指定转向角，例如15度
next_state, done = env.step(steering_angle) # 应用动作，得到下一状态
env.render() # 可视化
```

![](img/7e912af13be2d5ea35ea005d087a22be_69.png)

![](img/7e912af13be2d5ea35ea005d087a22be_71.png)

### 2. 训练模拟器网络

![](img/7e912af13be2d5ea35ea005d087a22be_73.png)

![](img/7e912af13be2d5ea35ea005d087a22be_75.png)

![](img/7e912af13be2d5ea35ea005d087a22be_77.png)

![](img/7e912af13be2d5ea35ea005d087a22be_79.png)

![](img/7e912af13be2d5ea35ea005d087a22be_81.png)

以下是训练模拟器网络的核心代码结构：

```python
# 伪代码示例：训练模拟器
simulator_net = SimulatorNet(input_dim=7, hidden_dim=45, output_dim=6)
optimizer = torch.optim.Adam(simulator_net.parameters())

![](img/7e912af13be2d5ea35ea005d087a22be_83.png)

for episode in range(num_episodes):
    state = env.random_state()
    for step in range(steps_per_episode):
        steering = random.uniform(-45, 45)
        next_state_true = env.true_dynamics(state, steering) # 根据真实模型计算

        # 网络预测
        input_vec = torch.cat([state, steering])
        next_state_pred = simulator_net(input_vec)

        # 计算损失并更新
        loss = F.mse_loss(next_state_pred, next_state_true)
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()

        state = next_state_true
```

### 3. 训练控制器网络（概念）

训练控制器需要将控制器和模拟器连接起来：

```python
# 伪代码示例：训练控制器（概念性流程）
controller_net = ControllerNet(input_dim=6, hidden_dim=25, output_dim=1)
simulator_net.eval() # 冻结模拟器权重
optimizer = torch.optim.Adam(controller_net.parameters())

for episode in range(num_controller_episodes):
    states = []
    state = env.random_state()
    done = False
    step = 0

    # 前向传播：展开轨迹
    while not done and step < max_steps:
        steering = controller_net(state) # 控制器输出
        # 使用训练好的模拟器预测下一状态
        input_vec = torch.cat([state, steering])
        state = simulator_net(input_vec)
        states.append(state)
        step += 1
        # 检查是否到达终止条件（如接近码头）
        done = check_termination(state)

    # 计算最终状态的损失
    final_state = states[-1]
    loss = final_loss(final_state, dock_target) # 计算与目标码头的差距

    # 反向传播通过整个轨迹更新控制器
    optimizer.zero_grad()
    loss.backward() # 梯度会通过模拟器回溯到控制器
    optimizer.step()
```

![](img/7e912af13be2d5ea35ea005d087a22be_85.png)

![](img/7e912af13be2d5ea35ea005d087a22be_87.png)

![](img/7e912af13be2d5ea35ea005d087a22be_88.png)

---

## 总结与延伸

![](img/7e912af13be2d5ea35ea005d087a22be_90.png)

本节课中，我们一起学习了一个经典的神经网络控制案例——卡车倒车入库。

**核心要点总结**：
1.  **问题**：控制带有拖车的卡车倒车入库是一个复杂的非线性控制问题。
2.  **方法**：采用两阶段训练法。
3.  **第一阶段**：训练一个神经网络模拟器来学习系统的动力学模型。即使有解析模型，这种方法也更具通用性。
4.  **第二阶段**：将控制器网络与固定模拟器网络连接并展开，通过**随时间反向传播（BPTT）**，利用最终状态与目标状态的误差来训练控制器网络。这是一个用**固定目标训练可变深度网络**的巧妙应用。
5.  **关键**：模拟器网络的可微性是整个训练流程能够进行梯度反向传播的基础。

![](img/7e912af13be2d5ea35ea005d087a22be_92.png)

**延伸思考与练习**：
*   尝试在本课程提供的代码基础上，实现控制器网络的训练部分。
*   思考如何将这种方法应用于其他具有复杂动力学的系统（如机器人、无人机）。
*   对比这种方法与强化学习（如策略梯度）在解决此类问题上的异同。

![](img/7e912af13be2d5ea35ea005d087a22be_94.png)

通过动手实现，你将能更深入地理解如何利用神经网络来学习和控制复杂的动态系统。