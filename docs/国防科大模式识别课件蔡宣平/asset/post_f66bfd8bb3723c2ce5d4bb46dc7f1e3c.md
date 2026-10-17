
## 5.4 概密的窗函数估计法
### k_N-近邻估计法

N-1, K_N-1

N=16, K_N=4

N=256, K_N=16

N=∞, K_N=∞

## 作业

![](img/d893b90ad57f036ece52d376593dc2c5_569_0.png)

P170 5.7 5.8

```
#include <math.h>
#include <stdlib.h>
void gauss(double * x1,double *x2)
{//产生服从正态分布的随机数对，用变量参数x1与x2传递随机数
    double pi,r1,r2,s;
    pi=3.14159265;      //赋 π 值
    r1=rand()/RAND_MAX ;
    r2=rand()/RAND_MAX ;
    s=sqrt(-2*log(r1));      //中间变量赋值
    *x1=s*cos(2*pi*r2);
    *x2=s*sin(2*pi*r2);
    //正态分布随机数赋给变量参数
}
    //gauss
```

## 第五章 统计决策中的训练、学习与错误率测试、估计
### 5·5 有限项正交函数级数逼近法

#### 5·5 有限项正交函数级数逼近法—最小积分平方逼近方法

设有 $N$ 个抽自同一母体 $\vec{x}$ 的样本 $\vec{x}_1, \vec{x}_2, \cdots, \vec{x}_N$ 用于估计总体概密 $p(\vec{x})$，我们将概密 $p(\vec{x})$ 的估计 $\hat{p}(\vec{x})$ 表示成有限项正交级数

$\hat{p}(\vec{x}) = \sum_{i=1}^{R} C_i \varphi_i(\vec{x})$

式中，$\varphi_i(\vec{x})$ 是某一正交函数集 $\{\varphi_i(\vec{x})\}$ 的基函数，$C_i \ (i=1,2,\cdots,R)$ 为待定系数。

应根据 $p(\vec{x})$ 的特点适当选择 $\{\varphi_i(\vec{x})\}$ 以期在固定的项数下减小误差，项数 R 取得越大近似得就越好。

#### 5·5 有限项正交函数级数逼近法— 最小积分平方逼近方法

估计 $\hat{p}(\vec{x})$ 与真值 $p(\vec{x})$ 之间的误差可用下式测度

$J(C_1, C_2, \cdots, C_R) = \int_{\Omega} \rho(\vec{x}) \big(p(\vec{x}) - \hat{p}(\vec{x})\big)^2 d\vec{x}$

式中，$\Omega$ 是特征空间，$\rho(\vec{x})$是权函数，显然

$J(\cdot)$ 越小，我们得到的估计从总体上讲就越精确。

将 $\hat{p}(\vec{x})$ 的具体表示代入上式得：

$J(C_1, C_2, \cdots, C_R) = \int_{\Omega} \rho(\vec{x}) \big(p(\vec{x}) - \sum_{i=1}^{R} C_i \varphi_i(\vec{x})\big)^2 d\vec{x}$

$J(C₁, C₂, …, C_R) = ∫_Ω ρ(\vec{x}) (p(\vec{x}) - Σ_{i=1}^R C_i φ_i(\vec{x}))² d\vec{x}$

上式的 J 是 C_i (i = 1,2, …, R) 的二次函数，因此使 J 达到最小值的 C_i* 必要且只要满足：

∂J(C₁, C₂, …, C_R) / ∂C_k |_{C_i = C_i*, i=1,2,…,R} = 0      (k = 1,2, …, R)

由此可得：

2 ∫_Ω ρ(\vec{x}) (p(\vec{x}) - Σ_{i=1}^R C_i* φ_i(\vec{x})) (-φ_k(\vec{x})) d\vec{x} = 0

从而有：

Σ_{i=1}^R C_i* ∫_Ω ρ(\vec{x}) φ_i(\vec{x}) φ_k(\vec{x}) d\vec{x} = ∫_Ω ρ(\vec{x}) φ_k(\vec{x}) p(\vec{x}) d\vec{x}      (k = 1,2, …, R)

若使 $J$ 达最小的**充要条件**。显然右边是 $\rho(\vec{x})\varphi_k(\vec{x})$ 的数学期望，可用 $N$ 个独立抽取的样本函数平均近似。

$$\sum_{i=1}^{R}C_i^*\int_{\Omega}\rho(\vec{x})\varphi_i(\vec{x})\varphi_k(\vec{x})d\vec{x}\approx\frac{1}{N}\sum_{j=1}^{N}\rho(\vec{x}_j)\varphi_k(\vec{x}_j)\quad(k=1,2,\ldots,R)$$

令 $\{\varphi_i(\vec{x})\}$ 是带权函数 $\rho(\vec{x})$ 的正交函数集，即

$$\int_{\Omega}\rho(\vec{x})\varphi_i(\vec{x})\varphi_k(\vec{x})d\vec{x}=\begin{cases}A_i,&i=k\\0,&i\ne k\end{cases}$$

∑_{i=1}^{R} C_i^* ∫_Ω ρ(\vec{x}) φ_i(\vec{x}) φ_k(\vec{x}) d\vec{x} ≈ (1/N) ∑_{j=1}^{N} ρ(\vec{x}_j) φ_k(\vec{x}_j)      (k = 1,2,⋯,R)

∫_Ω ρ(\vec{x}) φ_i(\vec{x}) φ_k(\vec{x}) d\vec{x} = { A_i , i = k ; 0 , i ≠ k }

则有： C_i^* ≈ (1/(N A_i)) ∑_{j=1}^{N} ρ(\vec{x}_j) φ_i(\vec{x}_j)      (i = 1,2,⋯,R)

若{φ_i(\vec{x})}是在 ρ(\vec{x})下的规范化的正交函数集，即 A_i = 1

则有： C_i^* ≈ (1/N) ∑_{j=1}^{N} ρ(\vec{x}_j) φ_i(\vec{x}_j)      (i = 1,2,⋯,R)

将所求得的最佳系数 C_i^* 代入式 \hat{p}(\vec{x}) = ∑_{i=1}^{R} C_i φ_i(\vec{x})

便可以得到 \hat{p}(\vec{x})。

#### 5·5 有限项正交函数级数逼近法—最小积分平方逼近方法

C_i^* 的计算式可写成迭代形式。

令 ρ(x)=1，若 C_i^*(N) 表示用前 N 个样本所求得的系数

当加入第 N+1 个样本后，

C_i^*(N+1)= 1/(N+1)[ N C_i^*(N)+ φ_i(x_{N+1}) ]      (i=1,2,…,R)

初始系数: C_i^*(0)=0，显然 C_i^*(1)= φ_i(x_1)。

#### 5·5 有限项正交函数级数逼近法——最小积分平方逼近方法

同理可得到 $\hat{p}_{N+1}(\vec{x})$ 的迭代形式。

$\hat{p}_{N}(\vec{x}) = \sum_{i=1}^{R} C_{i}^{*}(N)\varphi_{i}(\vec{x}) \qquad \hat{p}_{N+1}(\vec{x}) = \sum_{i=1}^{R} C_{i}^{*}(N+1)\varphi_{i}(\vec{x})$

$C_{i}^{*}(N+1) = \frac{1}{N+1}\left[ N C_{i}^{*}(N) + \varphi_{i}(\vec{x}_{N+1}) \right]$

$\hat{p}_{N+1}(\vec{x}) = \frac{N}{N+1}\hat{p}_{N}(\vec{x}) + \frac{1}{N+1}\sum_{i=1}^{R} \varphi_{i}(\vec{x}_{N+1})\varphi_{i}(\vec{x})$

$= \hat{p}_{N}(\vec{x}) + \frac{1}{N+1}\left[ \sum_{i=1}^{R} \varphi_{i}(\vec{x}_{N+1})\varphi_{i}(\vec{x}) - \hat{p}_{N}(\vec{x}) \right]$

初始值：$\hat{p}_{0}(\vec{x}) = 0$

#### 5·5 有限项正交函数级数逼近法—最小积分平方逼近方法

前面介绍的方法中被逼近的函数是概密，对于这种幅值大小变化较剧烈的函数，须用较多的项才可能在整个空间中有较好的逼近。

为减少计算量，在样本出现较密集的区域（即概密取值较大的区域）中，应要求逼近精度高些；而在样本出现稀疏的区域（即概密取值较小的区域）中，可以让逼近精度低一些。

这样分别对待会使在相同的训练样本下总的误判概率较小。因此应考虑加权的最小均方差逼近。
