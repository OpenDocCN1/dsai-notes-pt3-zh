# # 回顾第三章：傅里叶变换 Fourier transform

# —1807: Joseph Fourier

+   - 傅立叶理论指出，一个信号可表示成一系列正弦和余弦函数之和，叫做傅立叶展开式

![](bbox=[0.219, 0.314, 0.781, 0.645])

$F(\omega)=\int_{-\infty}^{+\infty} f(t)e^{-j\omega t}\,dt$

$f(t)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}F(\omega)e^{j\omega t}\,d\omega$

where $e^{-j\omega t}=\cos\omega t-j\sin\omega t$

![](bbox=[0.75, 0.507, 0.933, 0.811])

+   - 只有频率分辨率而没有时间分辨率
+   - 可确定信号中包含哪些频率的信息，但不能确定具有这些频率的信号出现在什么时候