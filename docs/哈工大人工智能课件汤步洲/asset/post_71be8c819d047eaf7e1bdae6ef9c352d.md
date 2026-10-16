
## 5.1 概述
### 5.1.1 不确定性推理的含义
什么是确定性推理：

不确定性推理是指建立在不确定性知识和证据基础上的推理。包括不完备、不精确知识的推理，模糊知识的推理，非单调性推理等。这指除精确推理以外的其它各种推理问题。

不确定性推理过程实际上是一种从不确定的初始证据出发，通过运用不确定性知识，最终推出具有一定不确定性但却又是合理或基本合理的结论的思维过程。

为什么要采用不确定性推理

- 所需知识不完备、不精确
- 所需知识描述模糊
- 多种原因导致同一结论
- 解题方案不唯一

### 5.1.2 不确定性的表示
(1) 知识的不确定性的表示

考虑因素：问题的描述能力，推理中不确定性的计算

含义：知识的确定性程度，或动态强度

表示：用概率，[0,1]，0接近于假，1接近于真

用可信度，[-1,1]，大于0接近于真，小于0接近于假

(2) 证据不确定性的表示

证据的类型：按证据组织：基本证据，组合证据

按证据来源：初始证据，中间结论

表示方法：概率，可信度，模糊集等

基本证据：常与知识表示方法一致，如概率，可信度，模糊集等

组合证据：组合方式：析取的关系，合取的关系。

计算方法：基于基本证据

最大最小方法，概率方法，有界方法等。

### 5.1.3 不确定性推理
推理过程实际上是不断寻找可用知识并加以运用的过程。1）寻找可用知识时，不确定性的知识和证据之间如何匹配？2）运用不确定性知识和证据进行推理时，如何更新不确定性的结论（即产生式规则表示中的假设）

（1）不确定性的匹配
含义

不确定的前提条件与不确定的事实匹配

问题

前提是不确定的，事实也是不确定的

方法

设计一个计算相似程度的算法，给出相似的限度

标志

相似度落在规定限度内为匹配，否则为不匹配

### 5.1.3 不确定性推理
（2）不确定性的更新

主要问题

- ① 如何用证据的不确定性去更新结论的不确定性
- ② 如何在推理中把初始证据的不确定性传递给最终结论

解决方法

对①，不同推理方法的解决方法不同

对②，不同推理方法的解决方法基本相同，即把当前结论及其不确定性作为新的结论放入综合数据库，依次传递，直到得出最终结论

5. 不确定性结论的合成

含义：多个不同知识推出同一结论，且不确定性程度不同

方法：视不同推理方法而定

## 5.4 不确定性推理类型
![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_536_0.png)

### 5.1.4 不确定性推理类型
不确定性推理
├─ 非数值方法
│   ├─ 框架推理
│   ├─ 语义网络推理
│   ├─ 常识推理
│   └─ …
└─ 数值方法
    ├─ 概率方法
    │   ├─ 基于概率
    │   │   ├─ 可信度方法
    │   │   ├─ 主观Bayes方法
    │   │   └─ 证据理论
    │   └─ 概率推理
    └─ 模糊方法

### 5.1.4 不确定性推理类型
- 数值方法
  - 对不确定性的一种定量表示和处理方法
  - 其研究及应用较多，已形成多种应用模型
- 非数值方法
  - 除数值方法外的其它处理不确定性的模型方法
  - 典型代表：“发生率计算方法”，它采用集合来描述和处理不确定性，且满足概率推理的性质

### 5.1.4 不确定性推理类型
- 概率统计方法
  - 有完整、严密的数学理论
  - 为不确定性的合成与传递提供了现成的数学公式
  - 最早、最广泛地用于不确定性知识的表示与处理
  - 已成为不确定性推理的重要手段
- 证据理论方法
  - 1967年Dempster首次提出，1976年Shafer完善
  - 可表示并处理“不知道”等不确定性信息

### 5.1.4 不确定性推理类型
- 模糊推理方法
  - 可表示并处理由模糊性引起的不确定性
  - 已广泛应用于不确定性推理
- 粗糙集理论方法
  - 1981年Z. Pawlak首次提出
  - 一种新的可表示并处理“含糊”等不确定性的数学方法
  - 可用于不确定性推理、数据挖掘等领域

## 主要内容
- 5.1 概述
- 5.2 概率统计方法
- 5.3 Bayes网络

## 5.2 概率统计方法
- Probability
  - Random Variables
  - Joint and Marginal Distributions
  - Conditional Distribution
  - Product Rule, Chain Rule, Bayes’ Rule
  - Inference
  - Independence
  - IMPORTANT! ! !

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_542_0.png)

### Random Variables
- A random variable is some aspect of the world about which we (may) have uncertainty
  - R = Is it raining?
  - T = Is it hot or cold?
  - D = How long will it take to drive to work?
  - L = Where is the Pac-Man?
- We denote random variables with capital letters
- Random variables have domains
  - R in {true, false} (often write as {+r, -r}, Boolean random variables)
  - T in {hot, cold} (Discrete random variables)
  - D in [0, ∞) (Continuous random variables)
  - L in possible locations, maybe {(0,0), (0,1), ···}

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_543_0.png)

### Probability Distributions
- Associate a probability with each value

- Temperature:

- Weather:

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_544_0.png)

P(T)
| T | P |
|---|---|
| hot | 0.5 |
| cold | 0.5 |

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_544_1.png)

P(W)
| W | P |
|---|---|
| sun | 0.6 |
| rain | 0.1 |
| fog | 0.3 |
| meteor | 0.0 |

### Probability Distributions
- Unobserved random variables have distributions

| T | P |
|---|---|
| hot | 0.5 |
| cold | 0.5 |

| W | P |
|---|---|
| sun | 0.6 |
| rain | 0.1 |
| fog | 0.3 |
| meteor | 0.0 |

- A distribution is a TABLE of probabilities of values

P(W = rain) = 0.1

- Must have: ∀x P(X = x) ≥ 0 and ∑_x P(X = x) = 1

> Shorthand notation:
> 
> P(hot) = P(T = hot),
> P(cold) = P(T = cold),
> P(rain) = P(W = rain),
> ...
> 
> OK if all domain entries are unique

### Joint Distributions
- A joint distribution over a set of random variables: X₁, X₂, ... Xₙ specifies a real number for each assignment (or outcome or atomic event):

P(X₁ = x₁, X₂ = x₂, ... Xₙ = xₙ)

P(x₁, x₂, ... xₙ)

- Must obey:

P(x₁, x₂, ... xₙ) ≥ 0

∑₍x₁,x₂,...xₙ₎ P(x₁, x₂, ... xₙ) = 1

- Size of distribution if n variables with domain sizes d?

- For all but the smallest distributions, impractical to write out!

P(T, W)

| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |
