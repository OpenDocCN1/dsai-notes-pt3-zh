# 二、一次准则函数

**构造准则函数：** $J(\vec{w})=k\left(|\vec{w}^{\prime}\vec{x}|-\vec{w}^{\prime}\vec{x}\right)\quad(k>0)$

**当** $\vec{w}^{\prime}\vec{x}<0$ **时** $|\vec{w}^{\prime}\vec{x}|-\vec{w}^{\prime}\vec{x}=-2\vec{w}^{\prime}\vec{x}>0$

**当** $\vec{w}^{\prime}\vec{x}\geq 0$ **时** $|\vec{w}^{\prime}\vec{x}|-\vec{w}^{\prime}\vec{x}=0$

**故有极小值：** $J_{\min}(\vec{w})=0$

对于已符号规范化的训练模式，寻求使 $J(\vec{w})$ 取极小的 $\vec{w}$，此时的 $\vec{w}$ 满足 $\vec{w}^{\prime}\vec{x}\geq 0$