# 离散化Discretization

+   - 属性有三种
+     - 标称Nominal—values from an unordered set, e.g., color, profession
+     - 顺序Ordinal—values from an ordered set, e.g., military or academic rank
+     - 数值Numeric—real numbers, e.g., integer or real numbers

+   - 离散化Discretization: 将连续的属性分割为有间隔的
+     - 用间隔标签可以代替实际的数据值
+     - 通过离散化减少数据大小
+     - 监督的离散化Supervised vs. 非监督的离散化unsupervised
+     - 自顶向下离散化Split (top-down) vs. 自底向上离散化merge (bottom-up)
+     - 在一个属性值上可以递归地进行离散化
+     - 为进一步的分析做准备（如分类）