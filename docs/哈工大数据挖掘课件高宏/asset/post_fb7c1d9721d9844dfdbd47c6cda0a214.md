
## How to construct a decision tree?

- a tree is constructed in a top-down recursive divide-and-conquer manner
  - 首先，所有训练实例位于根节点
  - 所有属性都是可分类的属性（若为连续值，则事先离散化）
  - 根据选择的属性，对实例进行划分
    - a selected attribute is also called a split or a test
  - 可以用基于启发式或统计的方法来选择划分属性 (e.g. information gain)

## How to construct a decision tree?(cont.)

- 当下列条件之一成立时，划分过程结束：
  - 所有落入一个节点的实例属于相同的一个类
    - 该节点成为叶节点，并标注上类标识
  - 再没有其它属性来划分实例
    - 该节点成为叶节点，其类标识为落入该节点的多数实例的类标识
  - There are no samples left

## 训练集合

| ID | name | age | gender | Credit rating | Student | Buy computer |
|---|---|---|---|---|---|---|
| 1 | Smith | 35 | male | fair | Yes | yes |
| 2 | Tom | 38 | male | excellent | No | yes |
| 3 | Fred | 43 | male | fair | No | Yes |
| 4 | Marry | 55 | female | fair | No | Yes |
| 5 | Marry | 47 | female | excellent | No | No |
| 6 | Peter | 24 | male | fair | No | No |
| 7 | John | 18 | male | fair | Yes | Yes |
| 8 | Susan | 20 | female | fair | No | No |
| 9 | Jenny | 31 | female | excellent | Yes | yes |

![](img/76d573223e44fade1c0950849390a4b3_196_0.png)

## algorithm of the basic strategy (ID3):

Generate_decision_tree (samples, attribute_list)

## How to construct a decision tree?(cont.)

- **Attribute Selection Measure**
  Information Gain (ID3/C4.5)
  Select the attribute with the highest information gain
  - the information needed to correctly classify all the instances
  - entropy of attribute A
  - information gained by branching on attribute A

## 关于熵

- Shannon 的信息论
- 一组数据中的平均信息量，成为熵
- 熵的定量表示
  - 设有三种消息按不规则的次序出现，一共 n 个。
  - 三个消息出现的概率为 p₁,p₂,p₃
  - n 个消息中含有的消息数为： np₁,np₂,np₃
  - 一个消息所含的信息量为 -log p₁, -log p₂, -log p₃

| 消息出现的概率 | 1个消息的信息量 | n 中的消息个数 | 它的信息量 |
|---|---|---|---|
| p₁ | -log p₁ | n p₁ | - n p₁ log p₁ |
| p₂ | -log p₂ | n p₂ | - n p₂ log p₂ |
| p₃ | -log p₃ | n p₃ | - n p₃ log p₃ |

| 消息出现的概率 | 1个消息的信息量 | n中的消息个数 | 它的信息量 |
|---|---|---|---|
| p₁ | -log p₁ | n p₁ | - n p₁ log p₁ |
| p₂ | -log p₂ | n p₂ | - n p₂ log p₂ |
| p₃ | -log p₃ | n p₃ | - n p₃ log p₃ |

- 则全部信息量为：
  -n p₁ log p₁ - n p₂ log p₂ - n p₃ log p₃
- 平均信息量(熵)为：
  (-n p₁ log p₁ - n p₂ log p₂ - n p₃ log p₃)/n
  = -p₁ log p₁ - p₂ log p₂ - p₃ log p₃
- 熵的一般形式为：
  $I = -\sum_{i} p_i \log p_i$

- 熵描述了信息的不确定性，不确定性越大，熵也就越大，把它搞清楚所需要的信息量也就越大。
- 一个系统越是有序，信息熵就越低；
- 反之，一个系统越是混乱，信息熵就越高。所以，信息熵也可以说是系统有序化程度的一个度量。

S: training set
S_i: training instances of class C_i(i= 1, ..., m)
a_j: values of attribute A(j= 1, ..., v)

平均信息量（熵）：表示分类在训练集中分布的不确定性
I(S1,S2,...,Sm) = - Σ_{i=1}^{m} |S_i|/|S| log₂ |S_i|/|S|

条件熵：已知属性A的分类分布后，分类在训练集中分布的不确定性。A with values {a₁,a₂,...,a_v}
E(A)= Σ_{j=1}^{v} |S₁j|+...+|S_mj| / |S| I(S1j,...,Smj)

信息增益 by branching on attribute A

the bigger the information gain, the better the attribute A

## Example of information gain (I)

training set:

S₁: buys_computer = “yes”, S₂: buys_computer = “no”

| rid | age | income | student | credit_rating | Class: buys_computer |
|---|---|---|---|---|---|
| 1 | <30 | high | no | fair | no |
| 2 | <30 | high | no | excellent | no |
| 3 | 30-40 | high | no | fair | yes |
| 4 | >40 | medium | no | fair | yes |
| 5 | >40 | low | yes | fair | yes |
| 6 | >40 | low | yes | excellent | no |
| 7 | 30-40 | low | yes | excellent | yes |
| 8 | <30 | medium | no | fair | no |
| 9 | <30 | low | yes | fair | yes |
| 10 | >40 | medium | yes | fair | yes |
| 11 | <30 | medium | yes | excellent | yes |
| 12 | 30-40 | medium | no | excellent | yes |
| 13 | 30-40 | high | yes | fair | yes |
| 14 | >40 | medium | no | excellent | no |

the information needed to correctly classify the training set is

I(S₁, S₂) = I(9, 5) = - 9/14 log₂ 9/14 - 5/14 log₂ 5/14 = 0.940

I(S₁, S₂) = I(9, 5) = 0.940

# Compute the entropy for age:

for age = “< 30”: S₁₁ = 2, S₂₁ = 3
I(S₁₁, S₂₁) = − 2/5 log₂ 2/5 − 3/5 log₂ 3/5 = 0.971

for age = “30-40”: S₁₂ = 4, S₂₂ = 0
I(S₁₂, S₂₂) = 0

for age = “> 40”: S₁₃ = 3, S₂₃ = 2
I(S₁₃, S₂₃) = − 3/5 log₂ 3/5 − 2/5 log₂ 2/5 = 0.971

then the entropy of age is
E(age) = 5/14 I(S₁₁, S₂₁) + 4/14 I(S₁₂, S₂₂) + 5/14 I(S₁₃, S₂₃) = 0.694

then the information gain of selecting age is
Gain(age) = I(S₁, S₂) − E(age) = 0.246

# The information gain of other attributes:

Gain(income) = 0.029
Gain(student) = 0.151
Gain(credit_rating) = 0.048

| age | income | student | credit_rating | buys_computer |
| <=30 | high | no | fair | no |
| <=30 | high | no | excellent | no |
| 31...40 | high | no | fair | yes |
| >40 | medium | no | fair | yes |
| >40 | low | yes | fair | yes |
| >40 | low | yes | excellent | no |
| 31...40 | low | yes | excellent | yes |
| <=30 | medium | no | fair | no |
| <=30 | low | yes | fair | yes |
| >40 | medium | yes | fair | yes |
| <=30 | medium | yes | excellent | yes |
| 31...40 | medium | no | excellent | yes |
| 31...40 | high | yes | fair | yes |
| >40 | medium | no | excellent | no |

age is selected as the split for partitioning the training set

![](img/76d573223e44fade1c0950849390a4b3_204_0.png)
