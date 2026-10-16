

![](img/a04b187c89c5018c5ef6132980e27196_294_0.png)

# TensorFlow

# 目录

+   1. 基本概念
+   2. 示例解析
+   3. 特性

## 01 基本概念

### 数据流图（tf.Graph）

![](img/a04b187c89c5018c5ef6132980e27196_296_0.png)

- TensorFlow 是基于图（Graph）的计算系统。
- 图的节点由操作（Operation）构成，而图中各节点之间则由张量（Tensor）作为边连接起来。
- 数据流图表示计算指令之间的依赖关系和组合方式，包含图结构信息。
- 构建数据流图时并不会真正触发计算。
- 数据流图的优点在于能够合理安排各个操作之间的并行或顺序执行，协同不同的底层设备，并避免冗余操作。

![](img/a04b187c89c5018c5ef6132980e27196_297_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_297_1.png)

张量（tf.Tensor）

![](img/a04b187c89c5018c5ef6132980e27196_297_2.png)

- **dtype**：tf.float32、tf.int8 等，数据类型
- **Shape**：(n1, n2, n3)，数据形状
- **Name**：tensor1，数据名称
- **Op**：该 tensor 的来源操作
- **Graph**：该 tensor 所属的图
- ...

- ◆ 万物皆为张量
- ◆ 张量包括常量、变量、占位符等
- ◆ 涉及的数据都是张量

操作（tf.Operation）

tf.add

tf.subtract

tf.multiply

tf.divide

tf.layer.conv2d

图像  
卷积特征

接收零个或多个 Tensor 对象作为输入，然后生成零个或多个 Tensor 对象作为输出。

### 会话（tf.Session）

![](img/a04b187c89c5018c5ef6132980e27196_299_0.png)

- 图构建完成后，需要通过会话执行计算。
- 拥有具体的物理资源（如 CPU、GPU）。
- 提供执行 Operation 和计算 Tensor 值的环境。
- 计算 Graph 时，并不一定会计算 Graph 中的所有节点，而是只计算指定的节点，或计算所需节点的输出结果。

可视化（TensorBoard）

![](img/a04b187c89c5018c5ef6132980e27196_300_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_300_1.png)

数据流图、绘制分析图、显示附加数据等。

### 整体流程

- 1. 创建图（Graph）  
- 2. *创建占位符（Placeholder）  
- 3. 为图添加操作（Operation）  
- 4. 创建会话  
- 5. 执行计算

![](img/a04b187c89c5018c5ef6132980e27196_301_0.png)

## 02 示例解析

```
```python
# 导入模块
import numpy as np
import tensorflow as tf
```
```

```
# 导入模块
import numpy as np
import tensorflow as tf
# 准备训练数据
train_X = np.random.normal(1, 5, 200) # 输入特征
train_Y = 0.5*train_X+2+np.random.normal(0, 1, 200) # 训练目标
L = len(train_X) # 样本量
# 定义训练超参数
epoch = 200 # 纪元数（使用全部训练数据一次为 1 个纪元）
learn_rate = 0.005 # 学习率
```

```
# 准备训练数据
train_X = np.random.normal(1, 5, 200) # 输入特征
train_Y = 0.5*train_X+2+np.random.normal(0,1,200) # 训练目标
L = len(train_X) # 样本量
# 定义训练超参数
epoch = 200 # 纪元数（使用全部训练数据一次为 1 个纪元）
learn_rate = 0.005 # 学习率
# 定义数据流图
temp_graph = tf.Graph()
with temp_graph.as_default():
    X = tf.placeholder(tf.float32) # 定义张量占位符
    Y = tf.placeholder(tf.float32)
    k = tf.Variable(np.random.randn(), dtype=tf.float32)
    b = tf.Variable(0, dtype=tf.float32) # 定义变量
    linear_model = k*X+b # 线性模型
    cost = tf.reduce_mean(tf.square(linear_model - Y)) # 代价函数
    optimizer = tf.train.GradientDescentOptimizer(learning_rate=learn_rate) # 梯度下降算法
    train_step = optimizer.minimize(cost) # 最小化代价函数
    init = tf.global_variables_initializer() # 使用变量全局初始化选项
```

![](img/a04b187c89c5018c5ef6132980e27196_305_0.png)

```
# 定义数据流图
temp_graph = tf.Graph()
with temp_graph.as_default():
    X = tf.placeholder(tf.float32) # 定义张量占位符
    Y = tf.placeholder(tf.float32)
    k = tf.Variable(np.random.randn(), dtype=tf.float32)
    b = tf.Variable(0, dtype=tf.float32) # 定义变量
    linear_model = k*X+b # 线性模型
    cost = tf.reduce_mean(tf.square(linear_model - Y)) # 代价函数
    optimizer = tf.train.GradientDescentOptimizer(learning_rate=learn_rate) # 梯度下降算法
    train_step = optimizer.minimize(cost) # 最小化代价函数
    init = tf.global_variables_initializer() # 使用变量全局初始化选项
# 创建会话
```

```
with tf.Session(graph=temp_graph) as sess:
    sess.run(init) # 变量初始化
    for i in range(epoch):
        sess.run(train_step, feed_dict={X: train_X, Y: train_Y}) # 运行 “最小化代价函数”
        temp_cost = sess.run(cost, feed_dict={X: train_X, Y: train_Y}) # 代价函数
```

## 03 使用特点

- 1. 高度灵活（相对于 Caffe）：Python \ 完整的基本操作
- 2. 自动求导：定义模型 -> 结合损失函数
- 3. 多语言支持：Python \ C++ ...
- 4. Keras：第三方 API
- 5. 支持分布式
- 6. 可移植性：PC \ 服务器 \ 手机...

