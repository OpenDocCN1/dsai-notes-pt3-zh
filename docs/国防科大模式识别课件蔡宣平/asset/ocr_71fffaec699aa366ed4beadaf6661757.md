R_j(\vec{x}) = \sum_{i=1}^{c} \lambda_{ij} p(\vec{x}|\omega_i) P(\omega_i) / p(\vec{x})

对于两类问题，

R_1(\vec{x}) = [\lambda_{11} p(\vec{x}|\omega_1) P(\omega_1) + \lambda_{21} p(\vec{x}|\omega_2) P(\omega_2)] / p(\vec{x})

R_2(\vec{x}) = [\lambda_{12} p(\vec{x}|\omega_1) P(\omega_1) + \lambda_{22} p(\vec{x}|\omega_2) P(\omega_2)] / p(\vec{x})

如果 R_1(\vec{x}) \lessgtr R_2(\vec{x}) 则： \vec{x} \in \begin{cases} \omega_1 \\ \omega_2 \end{cases}

# 此时最小损失判决规则可以表为：

\lambda_{11} p(\vec{x}|\omega_1) P(\omega_1) + \lambda_{21} p(\vec{x}|\omega_2) P(\omega_2) \lessgtr \lambda_{12} p(\vec{x}|\omega_1) P(\omega_1) + \lambda_{22} p(\vec{x}|\omega_2) P(\omega_2)