# 其他可选的误差函数

+   - 为权值增加一个惩罚项
+     - 把一个随着权向量幅度增长的项加入到E中，这导致梯度下降搜寻较小的权值向量，从而减小过度拟合的风险，等价于使用权衰减策略
+     - $E(\tilde{w}) = \frac{1}{2} \sum_{d \in D} \sum_{k \in outputs} (t_{kd} - o_{kd})^2 + \gamma \sum_{i,j} w_{ji}^2$

+   - 对误差增加一项目标函数的斜率或导数
+     - 某些情况下，训练信息中不仅有目标值，而且还有关于目标函数的导数
+     - $E(\tilde{w}) = \frac{1}{2} \sum_{d \in D} \sum_{k \in outputs} \left[ (t_{kd} - o_{kd})^2 + \mu \sum_{j \in inputs} \left( \frac{\partial t_{kd}}{\partial x_d^j} - \frac{\partial o_{kd}}{\partial x_d^j} \right)^2 \right]$