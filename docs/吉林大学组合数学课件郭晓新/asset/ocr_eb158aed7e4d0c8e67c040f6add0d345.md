# 无序分拆

即 ln P(N) < \frac{2y}{1-y} - N ln y = \frac{2y}{1-y} + N(-ln y).

当 0 < y < 1 时有
-ln y = ln \frac{1}{y} < \frac{1}{y} - 1 = \frac{1 - y}{y},

所以有
ln P(N) < \frac{2y}{1-y} + N \frac{1 - y}{y}.

取 y = \frac{\sqrt{N}}{\sqrt{N}+1} 代入上式得
ln P(N) < 3\sqrt{N},

这就得到 P(N) < e^{3\sqrt{N}}

这个定理给出了关于 P(N) 的一个上界。