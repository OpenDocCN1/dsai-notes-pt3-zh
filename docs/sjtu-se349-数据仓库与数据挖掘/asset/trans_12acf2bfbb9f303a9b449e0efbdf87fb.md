

## CBR问题的求解

### Compare New Problem and Case 1

+ Problem (Symptom)
+ - Prob.: Break light doesn't work
+ - Car: Audi 80
+ - Year: 1989
+ - Battery voltage: 12.6 V
+ - State of lights: OK

+ Problem (Symptoms)
+ - Problem: Front light doesn't work
+ - Car: VW Golf II, 1.6 L
+ - Year: 1993
+ - Battery voltage: 13.6 V
+ - State of lights: OK
+ - State of light switch: OK

+ Solution
+ - Diagnosis: Front light fuse defect
+ - Repair: Replace front light fuse

Very important feature: weight = 6
Less important feature: weight = 1

### Similarity Computation by Weighted Average

similarity(new,case 1) = 1/20 * [ 6*0.8 + 1*0.4 + 1*0.6 + 6*0.9 + 6* 1.0 ] = 0.86

## CBR问题的求解

### Compare New Problem and Case 2

+ Problem (Symptom)
+ - Prob.: Break light doesn't work
+ - Car: Audi 80
+ - Year: 1989
+ - Battery voltage: 12.6 V
+ - State of lights: OK

+ Problem (Symptoms)
+ - Problem: Front light doesn't work
+ - Car: Audi A6
+ - Year: 1995
+ - Battery voltage : 12.9 V
+ - State of lights: surface damaged
+ - State of light switch: OK

+ Solution
+ - Diagnosis: Bulb defect
+ - Repair: Replace front light

Very important feature: weight = 6
Less important feature: weight = 1

### Similarity Computation by Weighted Average

similarity(new, case 2) = 1/20 * [ 6*0.8 + 1*0.8 + 1*0.4 + 6*0.95 + 6* 0 ] = 0.585

Case 1 is more similar: due to feature “State of lights”

## CBR学习的过程

### Reuse the Solution of Case 1

| CASE 1 |  |
|---|---|
| Problem (Symptoms):<br>- Front light doesn't work<br>- ... |  |
| Solution:<br>- Diagnosis: Front light fuse defect<br>- Repair: Replace front light fuse |  |

+ Problem (Symptom):
+ - Prob: Break light doesn't work
+ - Car: Audi 80
+ - Year: 1989
+ - Battery voltage: 12.6 V
+ - state of break light: OK

Adapt Solution:
How do differences in the problem affect the solution?

+ New Solution:
+ - Diagnosis: Break light fuse defect
+ - Repair: Replace break light fuse

## CBR学习的过程

### CBR Cycle

(Aamodt & Plaza, 1994, AI Communications)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1038_0.png)

## CBR学习一般过程

![](img/6d25e92eb0bd56a22c311279c19b06b4_1039_0.png)

## CBR中案例的存储

### Store the New Experience

If diagnosis is correct:
store new case in the memory.

| CASE 3 | Problem (Symptoms): |
|---|---|
|  | • Problem: Break light doesn’t work<br>• Car: Audi 80<br>• Year: 1989<br>• Battery voltage: 12.6 V<br>• State of break lights: OK<br>• light switch clicking: OK |
|  | Solution:<br>• Diagnosis: break light fuse defect<br>• Repair: replace break light fuse |

## CBR的主要研究问题

（1）范例表示：基于范例推理方法的效率和范例表示紧密相关。范例表示涉及这样几个问题：

+ - 选择什么信息存放在一个范例中
+ - 如何选择合适的范例内容描述结构
+ - 范例库如何组织和索引
+ - 对于那些数量达到成千上万、而且十分复杂的范例，组织和索引问题尤其重要。

（2）分析模型：分析模型用于分析目标范例，从中识别和抽取检索源范例库的信息。

（3）范例检索：利用检索信息从源范例库中检索并选择潜在可用的源范例。基于范例推理方法和人类解决问题的方式很相近。碰到一个新问题时，首先是从记忆或范例库中回忆出与当前问题相关的最佳范例。后面所有工作能否发挥出应有的作用，很大程度上依赖于这一阶段得到的范例质量的高低，因此这步非常关键。一般讲，范例匹配不是精确的，只能是部分匹配或近似匹配。

+ - 它要求有一个相似度的评价标准。该标准定义得好，会使得检索出的范例十分有用，否则将会严重影响后面的过程。

## CBR的主要研究问题

(4) **类比映射**：寻找目标范例同源范例之间的对应关系。

(5) **类比转换**：转换源范例中同目标范例相关的信息，以便应用于目标范例的求解过程中。其中，涉及到对源范例的求解方案的修改。把检索到的源范例的解答复用于新问题或新范例之中。

+ - 源范例与目标范例间有何不同之处
+ - 源范例中的哪些部分可以用于目标范例
+ - 对于简单的分类问题，仅需要把源范例的分类结果直接用于目标范例。它无需考虑它们之间的差别，因为实际上范例检索已经完成了这项工作。
+ - 而对于问题求解之类的问题，则需要根据它们之间的不同对复用的解进行调整。

(6) **解释过程**：对把转换过的源范例的求解方案应用到目标范例时所出现的失败做出解释，给出失败的因果分析报告。有时对成功也同样做出解释。基于解释的索引也是一种重要的方法。

(7) **范例修补**：有些类似于类比转换，区别在于修补过程的输入是解方案和一个失败报告，而且也许还包含一个解释，然后修改这个解以排除失败的因素。

## CBR的主要研究问题

(8) 类比验证: 验证目标范例和源范例进行类比的有效性。

(9) 范例保存: 新问题得到了解决，则形成了一个可能用于将来情形与之相似的问题。这时有必要把它加入到范例库中。这是学习也是这是知识获取。此过程涉及选取哪些信息保留，以及如何把新范例有机集成到范例库中。修改和精化源范例库，其中包括泛化和抽象等过程。

在决定选取范例的哪些信息进行保留时，一般要考虑以下几点：

+ - 和问题有关的特征描述
+ - 问题的求解结果
+ - 以及解答为什么成功或失败的原因及解释

把新范例加入到范例库中，需要对它建立有效的索引，这样以后才能对之作出有效的回忆。索引应使得与该范例有关时能回忆得出，与它无关时不应回忆出。为此，可能要对范例库的索引内容甚至结构进行调整，如改变索引的强度或特征权值。

## CBR的主要工具

+ - **CBR Design Explorer – Diagnostic & Design Shell**
  (Artificial Intelligence Applications Institute at University of Edinburgh)
+ - **CBR Framework for Bioprocessing**
  (Bioprocesses Group at VTT Biotechnology and Food Research)
+ - **CBR Tools – object oriented software library in JAVA**
  (AID research group at INRIA Sophia Antipolis)
+ - **CBR–Works product family – CBR shell (research licenses available)**
  (tec:inno GmbH )
+ - ……

