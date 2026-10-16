# 距离加权最近邻算法

+   - 对k-近邻算法的一个改进是对k个近邻的贡献加权，越近的距离赋予越大的权值，比如：
+     \(\tilde{f}(x_q) \leftarrow \arg\max_{v \in V} \sum_{i=1}^{k} w_i \delta(v, f(x_i))\quad w_i = \frac{1}{d(x_q, x_i)^2}\)
+   - 为了处理查询点x_q恰好匹配某个训练样例x_i，从而导致d(x_q,x_i)^2为0的情况，令这种情况下的\(\tilde{f}(x_q)\)等于f(x_i)，如果有多个这样的训练样例，我们使用它们占多数的分类
+   - 也可以用类似的方式对实值目标函数进行距离加权，用下式代替表8-1中的计算式，w_i的定义与前相同
+     \(\tilde{f}(x_q) \leftarrow \frac{\sum_{i=1}^{k} w_i f(x_i)}{\sum_{i=1}^{k} w_i}\)