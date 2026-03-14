知识表示与推理：P66：递归定义与类别定义 🧠

在本节课中，我们将学习如何使用递归逻辑来定义家族关系中的“祖先”关系，并探讨如何基于现有关系定义新的类别（如“母亲”）。我们还将讨论不同定义方式对推理效率的影响，并指出逻辑表达中常见的错误。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_1.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_3.png)

---

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_5.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_7.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_9.png)

上一节我们介绍了如何使用“父母”和“性别”等基本关系来定义“兄弟”、“姐妹”等近亲关系。本节中，我们来看看如何定义那些跨越任意多代的关系，例如“祖先”。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_11.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_13.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_15.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_17.png)

### 递归定义祖先关系

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_19.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_21.png)

对于像“祖先”这样可能跨越任意多代的关系，我们无法为每一代都写出明确的定义，否则知识库会变得过于庞大。幸运的是，我们可以使用递归逻辑来定义它。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_23.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_25.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_27.png)

一个递归定义通常包含两部分：**基础子句**和**递归子句**。以下是“祖先”关系的一种递归定义思路：

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_29.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_31.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_33.png)

*   **基础子句**：如果A是B的父母，那么A是B的祖先。
*   **递归子句**：如果A是P的祖先，并且P是X的父母，那么A是X的祖先。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_35.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_37.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_38.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_40.png)

这个定义可以用一阶逻辑公式清晰地表达出来。以下是其逻辑表示：

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_42.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_44.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_45.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_47.png)

**基础子句公式**：
`∀A, X: Parent(A, X) → Ancestor(A, X)`

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_49.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_51.png)

**递归子句公式**：
`∀A, X, P: (Parent(P, X) ∧ Ancestor(A, P)) → Ancestor(A, X)`

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_52.png)

这个定义的含义是：要判断A是否是X的祖先，我们可以从X出发，查看X的父母（P）。如果A恰好是X的父母（基础情况），或者A是X的某位父母（P）的祖先（递归情况），那么A就是X的祖先。由于每个人通常有两个父母，这个定义在实际推理时会涉及搜索。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_54.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_55.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_57.png)

### 不同定义方式的效率考量

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_59.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_61.png)

我们刚刚给出的定义是从后代（X）向祖先（A）方向进行搜索的。但定义也可以从祖先向后代方向进行。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_63.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_65.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_67.png)

以下是另一种可能的定义方式（从祖先向下搜索）：
*   **基础子句**：`∀A, X: Parent(A, X) → Ancestor(A, X)`
*   **递归子句**：`∀A, X, P: (Parent(A, P) ∧ Ancestor(P, X)) → Ancestor(A, X)`

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_69.png)

那么，哪种定义更高效呢？这取决于具体的查询类型：
*   如果查询是“找出X的所有祖先”，从X向上搜索（第一种定义）可能更直接。
*   如果查询是“找出A的所有后代”，从A向下搜索（第二种定义）可能更直接。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_71.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_73.png)

此外，效率还受**分支因子**影响。在家族树中，一个人通常只有两个父母（向上分支因子为2），但可能有多个孩子（向下分支因子可变）。因此，从后代向上搜索的路径通常是确定的（两条），而从祖先向下搜索可能需要探索更多分支。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_75.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_77.png)

**思考**：请思考以下定义是否有效？为什么？
`∀A, X: Ancestor(A, X) ↔ (Parent(A, X) ∨ (∃P: Ancestor(A, P) ∧ Ancestor(P, X)))`

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_79.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_81.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_83.png)

### 逻辑表达中的常见错误

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_85.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_87.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_89.png)

在将自然语言表述转化为逻辑公式时，一个常见的错误是**省略变量的类别约束**。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_91.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_93.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_94.png)

**错误示例**：
“每个学生都喜欢某门课程。”如果直接写成：
`∀s ∃c: Likes(s, c)`
这个公式的意思是“对于域中的每一个个体s，都存在某个个体c，使得s喜欢c”。这显然过于宽泛，因为它可能包含了不是学生或课程的个体（比如，一只猫喜欢一条鱼）。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_96.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_98.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_100.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_102.png)

**正确写法**：
必须明确限定变量s和c的类别：
`∀s: Student(s) → (∃c: Course(c) ∧ Likes(s, c))`
这个公式的意思是：“对于所有个体s，如果s是学生，那么存在一个个体c，c是课程，并且s喜欢c。”这样就准确表达了原意。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_104.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_106.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_107.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_109.png)

在后续课程中，我们会接触到**描述逻辑**或**类型化逻辑**，它们能更自然地处理类别/类型问题，但在一阶逻辑中，我们必须显式地写出这些约束。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_111.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_112.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_114.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_115.png)

### 基于关系定义新类别

我们不仅可以定义关系，还可以利用现有关系来定义新的类别或概念。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_117.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_118.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_119.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_121.png)

例如，我们可以定义“母亲”这个类别：
`Mother(x) ↔ Female(x) ∧ (∃c: Parent(x, c))`
这个定义的意思是：x是母亲，当且仅当x是女性，并且存在至少一个个体c是x的孩子。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_123.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_125.png)

这种定义方式非常有用。以下是更多练习建议：
*   尝试用逻辑定义“偶数”、“奇数”。
*   尝试定义“质数”。
*   尝试定义“斐波那契数”。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_127.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_129.png)

在后续关于**描述逻辑**的章节中，我们将专门学习如何形式化地定义和操作这类概念（称为“概念”），它们主要通过描述与其他概念的关系来构建，而不直接涉及具体的个体变量。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_130.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_132.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_133.png)

---

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_135.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_136.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_137.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_139.png)

本节课中我们一起学习了如何使用递归逻辑定义“祖先”这类任意深度的关系，比较了不同定义方向对推理效率的影响，纠正了逻辑表达中遗漏类别约束的常见错误，并掌握了通过存在量词和现有关系来定义新类别（如“母亲”）的方法。这些都是在知识表示中构建复杂、准确模型的基础技能。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_141.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_143.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_145.png)

下一节，我们将把目光从家族关系转移到图论领域，看看如何用逻辑来描述图的性质。