前面我们已经说过，当 $N \to \infty$ ，$x$ 的 $k$ 个已知类别的最近邻样本 $x_1, x_2, \cdots, x_k$ 以概率 1 收敛于 $x$ ，所以这 $k$ 个样本可以不标出下标，纭记为 $x$ 。对于给定的 $x$ 的条件错误率为

$P_{N \to \infty}^k(e|x)=P(\omega_1|x)\sum_{j=0}^{(k-1)/2} C_k^j P(\omega_1|x)^j P(\omega_2|x)^{k-j}$

$+P(\omega_2|x)\sum_{j=0}^{(k-1)/2} C_k^j P(\omega_2|x)^j P(\omega_1|x)^{k-j}$

$=P(\omega_1|x)\sum_{j=0}^{(k-1)/2} C_k^j P(\omega_1|x)^j \left[1-P(\omega_1|x)\right]^{k-j}$

$+\left[1-P(\omega_1|x)\right]\sum_{j=(k+1)/2}^{k} C_k^j P(\omega_1|x)^j \left[1-P(\omega_1|x)\right]^{k-j}$