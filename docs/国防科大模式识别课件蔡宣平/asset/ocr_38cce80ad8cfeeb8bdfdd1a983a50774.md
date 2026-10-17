# 7.2.3 基于后验概率的可分性判据

在信息论中，熵(Entropy)表示不确定性，熵越大不确定性越大。可以借用熵的概念来描述各类的可分性。

对于c类问题，给定各类的后验概率 $p(\omega_i|\vec{x})$ 可以写成如下形式：

\{ \begin{array}{cccc} \omega_1 & \omega_2 & \cdots & \omega_c \\ p(\omega_1|\vec{x}) & p(\omega_2|\vec{x}) & \cdots & p(\omega_c|\vec{x}) \end{array} \} \triangleq \{ \begin{array}{cccc} \omega_1 & \omega_2 & \cdots & \omega_c \\ p_1 & p_2 & \cdots & p_c \end{array} \}

# 熵的定义：

$H(\vec{x}) \triangleq H(\vec{p}) = -\sum_{i=1}^{c} p_i \log p_i = -\sum_{i=1}^{c} p(\omega_i|\vec{x}) \log p(\omega_i|\vec{x})$

由洛必达法则知：当 $p_i = 0$ 时 $p_i \log p_i = 0$