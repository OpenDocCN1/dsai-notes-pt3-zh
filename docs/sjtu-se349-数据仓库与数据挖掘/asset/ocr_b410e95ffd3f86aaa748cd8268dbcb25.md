# ID3构建决策树的算法过程

+   首先对outlook的sunny分支建立子树
+   — 找出样本数据集weather中outlook取值sunny的样本子集S_sunny
+   — 依次计算剩下三个属性对该样本子集S_sunny划分后的信息增益
+   — 建立sunny分支子树

子集 S_sunny 的熵为

```
Entropy(S_sunny) = Entropy(3/5, 2/5) = -3/5 log 3/5 - 2/5 log 2/5 = 0.971
```

① 属性 humidity 在数据子集 S_sunny 中有 2 个取值{high,normal}，且不同取值下类标号取值相同，即

```
Entropy_humidity(S_sunny) = Σ_{j=1}^k |S_j|/|S_sunny| Entropy(S_j) = |S_1|/|S_sunny| Entropy(S_1) + |S_2|/|S_sunny| Entropy(S_2) = 3/5 *0 + 2/5 *0 = 0
```

因此，属性 humidity 划分子集 S_sunny 的信息增益值为

```
Gain(S_sunny, humidity) = Entropy(S_sunny) - Entropy_humidity(S_sunny) = 0.971 - 0 = 0.971
```