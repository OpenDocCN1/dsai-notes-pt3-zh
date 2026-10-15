

从上面可以看出近邻法有方法简单的优点，但也存在这样一些缺点：

- （1）存储量和计算量都很大；
- （2）没有考虑决策的风险，如果决策的错误代价很大时，会产生很大的风险；
- （3）以上的分析——渐近平均错误率，都是建立在样本数趋向无穷大的条件下得来的，在实际应用时大多是无法实现的。

## 典型的惰性学习法介绍

- K-最近邻分类（k-nearest-neighbor classifier, KNN）
- 基于案例的推理（Case-Based Reasoning, CBR）

![](img/6d25e92eb0bd56a22c311279c19b06b4_1025_0.png)

## 基于案例的推理（Case-Based Reasoning）

### 基于案例的推理存在的挑战

- 找到一个好的相似性度量（例如，为了匹配子图）和组合解的合适方法

- 为索引训练案例选择显著的特征和开发有效的索引技术

- 准确性和有效性之间的折中

- 随着案例数增加，CBR变得更智能。然而，到达某一点之后，系统的有效性将随着搜索和处理相关案例所需要时间增加而受损

- 与最近邻分类一样，一种解决方案是编制训练数据库。为了提高性能，可以丢弃冗余的或未被证明有用的案例。然而，这些决策并非轮廓鲜明的，它们的自动处理仍然是一个活跃的研究领域

## CBR推理发展简况

### History of CBR in Europe

- *Michael M. Richter, U. Kaiserslautern, Germany: CBR for Expert Systems*
  - 1988-1991 Systems MOLTKE and PATDEX (technical diagnosis)
  - since 1991 Case-Based Planning: Systems Caplan/CbC, PARIS
  - since 1992 European Projects INRECA, INRECA-II
- *Ramon Mantaras, Enric Plaza, IIIA Blanes, Spain: CBR and ML*
  - 1990 Case-Based Learning for medical diagnosis
- *Agnar Aamodt, U. Trondheim, Norway: CBR and Knowledge Acquisition*
  - 1991 System CREEK: Integration of Cases and general knowledge
- *Mark Keane, Trinity College, Dublin: Cognitive Science*
  - since 1988 Theory of analogical reasoning

Since 1991 increasing interest in Europe (several new research groups)

- 1991 First German CBR Workshop (AKCBR, GWCBR)
- 1993 First European CBR Workshop (EWCBR)
- 1995 First International CBR Conference (ICCBR)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1029_0.png)

## CBR例

### A Simple Example: What's a Case?

- A case describes one particular diagnostic situation
- A case records several features and their specific values occurred in that situation
- A case is not a rule!!

![](img/6d25e92eb0bd56a22c311279c19b06b4_1030_0.png)

### A Case Base with Two Cases

- Each case describes one particular situation
- All cases are independent from each other

| CASE | Problem (Symptoms) |
|------|--------------------|
| CASE 1 | - Problem: Front light doesn't work<br>- Car: VW Golf II, 1.6 L<br>- Year: 1993<br>- Battery voltage: 13,6 V<br>- State of lights: OK<br>- State of light switch: OK |
|  | **Solution:**<br>- Diagnosis: Front light fuse defect<br>- Repair: Replace front light fuse |

| CASE | Problem (Symptoms) |
|------|--------------------|
| CASE 2 | - Problem: Front light doesn't work<br>- Car: Audi A6<br>- Year: 1995<br>- Battery voltage: 12,9 V<br>- State of lights: surface damaged<br>- State of light switch: OK |
|  | **Solution:**<br>- Diagnosis: Bulb defect<br>- Repair: Replace front light |

### Solving a New Diagnostic Problem

- A new problem must be solved
- We make several observations in the current situation
- Observations define a new problem
- Not all feature values must be known
- Note: The new problem is a case without solution part

| Feature | Value |
|---|---|
| Problem (Symptom) | Brake light doesn't work |
| Car | Audi 80 |
| Year | 1989 |
| Battery voltage | 12.6 V |
| State of lights | OK |

## CBR问题的求解

### Compare the New Problem with Each Case and Select the Most Similar Case

![](img/6d25e92eb0bd56a22c311279c19b06b4_1033_0.png)

- When are two cases similar?
- How to rank the cases according to their similarity?
- Similarity is the most important concept in CBR!!
- We can assess similarity based on the similarity of each feature
  - Similarity of each feature depends on the feature value.
  - BUT: Importance of different features may be different

### Similarity Computation

- Assignment of similarities for feature values.
- Express degree of similarity by a real number between 0 and 1

Examples:

- Feature: *Problem*
  - Front light doesn't work ↔ Brake light doesn't work — 0.8
  - Front light doesn't work ↔ Engine doesn't start — 0.4
- Feature: *Battery voltage* (similarity depends on the difference)
  - 12.6 V ↔ 13.6 V — 0.9
  - 12.6 V ↔ 6.7 V — 0.1
- Different features have different importance (weights)!
  - High importance: Problem, Battery voltage, State of lights, ...
  - Low importance: Car, Year, ...

