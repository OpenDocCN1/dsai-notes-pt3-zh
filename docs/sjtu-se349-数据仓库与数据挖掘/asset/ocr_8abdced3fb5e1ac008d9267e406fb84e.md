# 余弦相似性(Cont.)

+   - 当属性是二元属性时，余弦相似性函数可以用共享特征或属性来解释
+   - 如果 $x_i = 1$ 则意味着对象x有第i个属性
+   - 那么，$x \cdot y$ 是x和y共同具有的属性数，可以将余弦公式进行简单变种
+     $$sim(x,y) = \frac{x \cdot y}{x \cdot x + y \cdot y - x \cdot y}$$
+   - x和y所共有属性与x和y所有具有的属性个数之间的比率
+   - 被称为Tanimoto系数或Tanimoto距离