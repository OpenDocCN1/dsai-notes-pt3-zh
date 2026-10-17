# 证明：判别函数值的正负表示出特征点位于哪个半空间中。

两矢量 \(\vec n\) 和 \((\vec x-\vec p)\) 的数积为：

\[
\vec n^{\prime}(\vec x-\vec p)=\|\vec n\|\|\vec x-\vec p\|\cos(\vec n,(\vec x-\vec p))=\frac{\vec w_0^{\prime}\vec x+\vec w_{n+1}}{\|\vec w_0\|}
\]

当 \(\vec n\) 和 \((\vec x-\vec p)\) 夹角小于 \(90^\circ\) 时，即 \(\vec x\) 在 \(\vec n\) 指向的那个半空间中，\(\cos(\vec n,(\vec x-\vec p))>0\)；

反之，当 \(\vec n\) 和 \((\vec x-\vec p)\) 夹角大于 \(90^\circ\) 时，即 \(\vec x\) 在 \(\vec n\) 背向的半空间中，\(\cos(\vec n,(\vec x-\vec p))<0\)。

由于 \(\|\vec w_0\|>0\)，故 \(\vec n^{\prime}(\vec x-\vec p)\) 和 \(\vec w_0^{\prime}\vec x+\vec w_{n+1}\) 同号。