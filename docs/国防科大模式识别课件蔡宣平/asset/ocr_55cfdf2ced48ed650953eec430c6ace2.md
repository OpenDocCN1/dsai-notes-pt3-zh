$S_w = \frac{1}{2} C_1 + \frac{1}{2} C_2 = \begin{pmatrix} 3.5 & 1.5 \\ 1.5 & 3.5 \end{pmatrix}$

依据S_W进行DKLT，得到特征值 $\lambda_1 = 5, \lambda_2 = 2$

对应的特征向量分别为：

$\mu_1 = (0.707, 0.707)', \mu_2 = (0.707, -0.707)'$

因为总的均值向量为：

$m = \frac{1}{2} m_1 + \frac{1}{2} m_2 = (0, 0)'$

故类间离差阵S_B为：

$S_B = \frac{1}{2} m_1 m_1' + \frac{1}{2} m_2 m_2' = \begin{pmatrix} 16 & 8 \\ 8 & 4 \end{pmatrix}$

计算J(y1)与J(y2)：

$J(y_1) = \frac{\mu_1' S_B \mu_1}{\lambda_1} \approx 3.7, \; J(y_2) = \frac{\mu_2' S_B \mu_2}{\lambda_2} \approx 1$