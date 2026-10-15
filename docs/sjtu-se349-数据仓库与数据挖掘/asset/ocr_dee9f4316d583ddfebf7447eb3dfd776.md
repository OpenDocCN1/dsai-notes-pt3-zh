# 原始数据标准化

因为在实际应用中，往往存在指标的量纲不同，所以在计算之前须先消除量纲的影响，而将原始数据标准化。为了实现样本数据的标准化，应求样本数据的平均和方差。对数据矩阵Y作标准化处理，即对每一个指标分量作标准化变换，变换公式为：

```
$X_{ij} = \frac{Y_{ij} - \overline{Y}_j}{S_j} \begin{pmatrix} i = 1,2,\cdots n \\ j = 1,2,\cdots p \end{pmatrix}$
```

样本均值

```
$\overline{Y}_i = \frac{1}{n} \sum_{k=1}^{n} Y_{ki}$
```

样本标准差

```
$S_i = \sqrt{\frac{1}{n-1} \sum_{k=1}^{n} (Y_{ki} - \overline{Y}_i)^2}$
```