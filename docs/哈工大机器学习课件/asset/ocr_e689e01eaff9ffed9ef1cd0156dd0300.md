# 梯度下降法则的推导（3）

+   - 表4-1，训练线性单元的梯度下降算法
+   Gradient-Descent(training_examples, η)
+   training_examples中每个训练样例形式为序偶<x,t>，x是输入值向量，t是目标输出值，η是学习速率
+   - 初始化每个w_i为某个小的随机值
+   - 遇到终止条件之前，做以下操作
+     - 初始化每个Δw_i为0
+     - 对于训练样例training_examples中的每个<x,t>，做
+       - 把实例x输入到此单元，计算输出o
+       - 对于线性单元的每个权增量Δw_i，做
+         Δw_i ← Δw_i + η(t-o)x_i
+     - 对于线性单元的每个权w_i，做
+       w_i ← w_i + Δw_i