L_{ij}(x) 是 x 的线性函数，而 x 的各分量是正态分布的，故 L_{ij} 是正态分布的随机变量。

E_i[L_{ij}] = \bar{\mu}_i \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j) - \frac{1}{2} (\bar{\mu}_i + \bar{\mu}_j)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j) = \frac{1}{2} (\bar{\mu}_i - \bar{\mu}_j)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j)

令 r_{ij}^2 = (\bar{\mu}_i - \bar{\mu}_j)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j)

E_i[L_{ij}] \triangleq \bar L_{ij} = \frac{1}{2} r_{ij}^2 
L_{ij}(x) = x' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j) - \frac{1}{2} (\bar{\mu}_i + \bar{\mu}_j)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j)

Var_i[L_{ij}] = E_i[(L_{ij} - \bar L_{ij})^2]
= E_i[((x - \bar{\mu}_i)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j))^2]
= E_i[(\bar{\mu}_i - \bar{\mu}_j)' \Sigma^{-1} (x - \bar{\mu}_i)(x - \bar{\mu}_i)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j)]
= (\bar{\mu}_i - \bar{\mu}_j)' \Sigma^{-1} (\bar{\mu}_i - \bar{\mu}_j)
= r_{ij}^2