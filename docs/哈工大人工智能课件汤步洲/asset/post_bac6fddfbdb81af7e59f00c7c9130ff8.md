
# 状态4

Goto( a, b )    AT( robot, b )
                HOLDS( robot, box )
===================> TABLE( a )
                TABLE( b )

# 状态5

Setdown( b )    AT( robot, b )
                EMPTY( robot )
===================> ON( box, b )
                TABLE( a )
                TABLE( b )

# 状态6(目标状态)

Goto( b, c )    AT( robot, c )
                EMPTY( robot )
===================> ON( box, b )
                TABLE( a )
                TABLE( b )

# 例5：猴子摘香蕉问题

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_150_0.png)

A

B

C

解：分别定义描述状态谓词

SITE(x, y): x在y处； HANG(w,y):w悬挂在y处

ON(z): z站在箱子上； HOLDS(z): z手里拿着香蕉

变元的个体域：

x的个体域是{monkey, box}

y的个体域是{a, b, c}

z的个体域是{monkey}

w的个体域是{banana}

# • 初始状态S₀:
S₀ = SITE(Monkey,a) ∧ HANG(Banana,b) ∧ SITE(Box,c) ∧ ¬ON(Monkey) ∧ ¬HOLDS(Monkey)

> • 目标状态S_g:
> S_g = SITE(Monkey,b) ∧ ¬HANG(Banana,b) ∧ SITE(Box,b) ∧ ON(Monkey) ∧ HOLDS(Monkey)

# 定义四个操作:

+   • Goto(u, v): 猴子从 u 走到 v 处。
+   • Pushbox(v, w):猴子推着箱子从v走到w处。
+   • Climbbox: 猴子爬上箱子。
+   • Grasp: 猴子摘到香蕉。

# 各操作的条件和动作：

# Goto(u,v)

条件： ¬ON(Monkey), SITE(Monkey, u)

动作：删除表： SITE(Monkey, u) 添加表： SITE(Monkey, v)

# Pushbox(v,w)

条件： ¬ON(Monkey), SITE(Monkey, v), SITE(Box, v)

动作：删除表： SITE(Monkey, v), SITE(Box, v)

添加表： SITE(Monkey, w), SITE(Box, w)

# Climbbox

条件： ¬ON(Monkey), SITE(Monkey, w), SITE(Box, w)

动作：删除表： ¬ON(Monkey)

添加表： ON(Monkey)

# Grasp:

条件： ON(Monkey), SITE(Box, b), HANG(Banana, b)

动作：删除表： ¬HOLDS(Monkey), HANG(Banana, b)

添加表： HOLDS(Monkey), ¬HANG(Banana, b)

# • 猴子摘香蕉求解过程：

$S_0 = SITE(Monkey, a)$

$\land HANG(Banana, b)$

$\land SITE(Box, c)$

$\land \neg ON(Monkey)$

$\land \neg HOLDS(Monkey)$

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_154_0.png)

$S_1 = SITE(Monkey, c)$

$\land HANG(Banana, b)$

$\land SITE(Box, c)$

$\land \neg ON(Monkey)$

$\land \neg HOLDS(Monkey)$

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_154_1.png)

$S_2 = SITE(Monkey, b)$

$\land HANG(Banana, b)$

$\land SITE(Box, b)$

$\land \neg ON(Monkey)$

$\land \neg HOLDS(Monkey)$

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_155_0.png)

Sg = SITE(Monkey,b)
∧ ¬HANG(Banana,b)
∧ SITE(Box,b)
∧ ON(Monkey)
∧ HOLDS(Monkey)

Grasp

S₂ = SITE(Monkey,b)
∧ HANG(Banana,b)
∧ SITE(Box,b)
∧ ¬ON(Monkey)
∧ ¬HOLDS(Monkey)

Climbbox

S₃ = SITE(Monkey,b)
∧ HANG(Banana,b)
∧ SITE(Box,b)
∧ ON(Monkey)
∧ ¬HOLDS(Monkey)

# 2.2.5 谓词逻辑表示法的特点

1. 优点

+   (1) 严密性。可以保证其演绎推理结果的正确性，可以较精确的表达知识。

+   (2) 自然性。谓词逻辑是一种接近于自然语言的形式语言。

+   (3) 通用性。拥有通用的逻辑演算方法和推理的规则。

+   (4) 易于实现。用它表示的知识易于模块化，便于知识的增删及修改，便于在计算机上实现。

# 2. 局限性

（1）知识表示能力差。不便于表达和加入非确定性、启发性知识等。

（2）组合爆炸。在其推理过程中，随着事实数目的增大及盲目的使用推例规则，有可能形成组合爆炸。

（3）效率低。由于推理是根据形式逻辑进行的，把推理演算与知识含义截然分开，抛弃了表达内容中所含有的语义信息，往往使推理过程太冗长，降低了系统的效率。

# 人工智能

汤步洲、苏敬勇

哈尔滨工业大学（深圳）

计算机科学与技术学院

tangbuzhou@hit.edu.cn

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_158_0.png)

# 人工智能

哈尔滨工业大学（深圳）

计算机科学与技术学院 汤步洲

tangbuzhou@hit.edu.cn

# 第 2 章 知识表示

主要内容

+   - 2.1 知识与知识表示
+   - 2.2 一阶谓词逻辑表示法
+   - 2.3 产生式表示法
+   - 2.4 语义网络表示法
+   - 2.5 框架表示法

# 2.3 产生式表示法

+   > 1943年Post首先在一种计算形式体系中提出。
+   > 形式上很简单，但在一定意义上模仿了人类思考的过程。
+   > 60年代开始，成为专家系统基本的知识表示方法
+   
+   > 适合表示事实性知识和规则性知识；
+   > 容易描述事实、规则以及它们的不确定性度量；

# 2.3.1 知识的产生式表示方法

# 事实的表示

# 事实的概念

事实是断言一个语言变量的值或断言多个语言变量之间关系的陈述句。

语言变量的值: 例如，“雪是白的”

语言变量之间的关系: 例如，“王峰热爱祖国”

# 事实的表示

确定性知识:

(对象，属性，值)， 例如， (snow, color, white) 或(雪，颜色，白)。

其中，对象就是语言变量。

(关系，对象1，对象2)， 例如， (love, Wang Feng, country) 或(热爱，王峰，祖国)

非确定性知识:

(对象，属性，值，可信度因子)

其中，“可信度因子”是指该事实为真的相信程度。可⽤[0，1]之间的一个实数来表示。

# 规则的表示

规则的产生式表示形式常称为产生式规则，简称产生式或规则。

# 产生式的基本形式

P→Q

或者 IF P THEN Q

前提
（可用的条件）

结论
（应该执行的操作）

其中，P是产生式的前提，也称为前件，它给出了该产生式可否使用的先决条件。Q是一组结论或操作，也称为后件，它指出当P满足时，应该推出的结论或应该执行的动作。

# 产生式的简例

"如果王宏是计算机系学生，则王宏会编程序"

可用产生式表示为：

IF 该学生是计算机专业 THEN 该学生会编程序

# ❖ 知识的产生式表示方法

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_165_0.png)

# 2. 3. 2产生式系统的基本结构

综合数据库DB(Data Base)

+   (1) 存放推理过程的各种当前信息。
+   如：
+   问题的初始状态
+   输入的事实
+   中间结论及最终结论

(2) 作为推理过程选择可用规则的依据。推理过程中某条规则是否可用，是通过该规则的前提与DB中的已知事实的匹配来确定的。可匹配的规则称为可用规则。利用可用规则进行推理，将会得到一个结论。该结论若不是目标，将作为新的事实放入DB，成为以后推理的已知事实。

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_166_0.png)

规则库RB(Rule Base)

也称知识库KB(Knowledge Base)

+   (1) 作用
+   用于存放推理所需的所有规则，是整个产生式系统的知识集。是产生式系统能够进行推理的根本。

+   (2) 要求
+   知识的完整性、一致性、准确性、灵活性和可组织性
