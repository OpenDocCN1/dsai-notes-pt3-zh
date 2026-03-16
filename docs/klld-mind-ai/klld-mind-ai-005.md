# 005：问题为何困难（第二部分）🔍

![](img/3faa731ed6e7267f6bdba1ecec8d322c_0.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_1.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_3.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_5.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_7.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_8.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_9.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_10.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_11.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_13.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_14.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_16.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_17.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_18.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_20.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_22.png)

在本节课中，我们将继续探讨“问题为何困难”这一主题。上一节我们介绍了问题可能因定义不清或已被证明为不可能而变得困难。本节中，我们将扩展对“困难”的理解，探讨其他几种使问题变得棘手的类型，并引入计算机科学中用于衡量问题难度的核心概念——**增长阶**。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_23.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_24.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_25.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_27.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_29.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_30.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_31.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_32.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_34.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_35.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_36.png)

## 因不确定性而困难的问题

![](img/3faa731ed6e7267f6bdba1ecec8d322c_37.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_39.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_40.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_42.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_43.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_44.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_45.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_47.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_48.png)

有时，问题之所以困难，源于时空的本质。我们无法确切知道未来会发生什么，有时也无法完全确定过去发生了什么。这些问题都涉及某种**不确定性**。我们或许能做出或好或坏的猜测，但给出的答案总是带有一定程度的**不确定性**或**置信度**。在计算机编程中，处理这类问题常涉及**概率**或其他处理不确定性的形式化方法。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_49.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_51.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_53.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_54.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_56.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_57.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_58.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_59.png)

以下是几个因不确定性而困难的例子：

![](img/3faa731ed6e7267f6bdba1ecec8d322c_61.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_62.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_63.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_65.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_66.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_67.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_69.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_71.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_73.png)

*   **火星上过去是否存在生命？** 目前我们掌握的证据不足以给出确切的“是”或“否”答案。我们只能根据现有证据，给出“很可能存在”或“很可能不存在”这样的概率性回答。
*   **红袜队今年能赢得锦旗吗？** 这是一个关于未来事件的预测问题。我们无法给出确定性答案，但可以基于数据和模型，给出概率性的预测。有些程序或人的预测质量更高。
*   **这个物体/人/动物构成威胁吗？** 这是一个需要在现实时间中做出判断的问题。答案总是带有不确定性，并且“威胁”本身也有程度之分（轻微威胁或严重威胁），这增加了问题的复杂性。
*   **这个形状（例如屏幕上显示的‘0’）是椭圆吗？** 从严格的数学定义（一维曲线）来看，答案是否定的。但从直觉和实际应用角度看，我们可以说它“近似于”椭圆。回答“是”或“否”需要引入额外的描述性语言。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_75.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_77.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_78.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_79.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_81.png)

所有这些问题的共同点是，我们需要额外的工具（如概率、置信度、近似描述）来讨论和解决它们，因此它们本质上是困难的。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_83.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_85.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_86.png)

## 对人类简单但对计算机困难（或反之）的问题

![](img/3faa731ed6e7267f6bdba1ecec8d322c_88.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_90.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_92.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_93.png)

上一节我们提到，视觉和语言学习对人类来说似乎很自然，但从形式化角度看，它们对应的某些问题是**不可能**解决的。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_95.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_96.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_97.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_99.png)

*   **视觉问题（从2D恢复3D）**：从数学上讲，不可能从二维视网膜图像**可靠地**恢复出三维世界结构。这是一个**从n-1维恢复n维信息**的普遍不可能性问题。
*   **语言学习问题（从句子推导语法）**：给定有限数量的句子，要确定生成这些句子的**上下文无关文法**，这在形式上是**不可能**的，因为可能存在无限多个符合要求的文法。

然而，这些问题对我们具有至关重要的进化意义，因此我们必须“尽最大努力”去解决。我们通过使用**启发式方法**（经验法则）、猜测、先验知识等，做出**非常好的猜测**。例如，人类视觉系统极其擅长从2D图像推断3D结构，其局限性恰恰体现在**光学幻觉**上——幻觉之所以有趣，正是因为它揭示了视觉系统在进行智能猜测时的边界。

另一方面，也存在一些在计算机科学家看来“简单”，但对人类可能并不简单的问题：

*   **给定一个正数，求其平方根**：存在明确的算法，计算机可以快速可靠地完成。对人类来说需要一些训练和计算。
*   **给定一个上下文无关文法，生成一个句子**：这非常容易（与从句子推导文法相反）。
*   **给定100个包含100个变量的线性方程组，判断是否有解并求解**：这对人类来说极其困难，但计算机可以轻松编程解决。这类问题体现了计算机在某些计算密集型任务上的优势。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_101.png)

## 问题的增长阶：衡量难度随规模的变化

![](img/3faa731ed6e7267f6bdba1ecec8d322c_103.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_104.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_105.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_106.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_108.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_110.png)

现在，我们引入一种源自计算机编程、用于讨论问题难易程度的语言：**增长阶**。其核心思想是：衡量问题难度如何随着问题**规模**（用 `n` 表示）的**自然增长**而增加。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_112.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_113.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_114.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_115.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_116.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_118.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_120.png)

让我们通过一个例子来理解。考虑“猜数字”游戏：我心中想一个1到N之间的整数，你每次猜一个数，我会告诉你“高了”、“低了”还是“正确”。最优策略是每次都猜当前范围的**中位数**。这样，每次猜测都能将可能范围**缩小一半**。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_122.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_123.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_124.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_125.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_127.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_129.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_131.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_132.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_133.png)

*   如果N=10，最多需要约4次猜测。
*   如果N=100，最多需要约7次猜测。
*   如果N=1，000，000（一百万），最多需要约20次猜测。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_135.png)

可以看到，即使问题规模（数字范围）急剧增大，所需时间（猜测次数）增长得非常缓慢。这种问题具有**对数级**的增长阶（记作 **O(log n)**），是一种非常有利（缓慢）的增长，意味着即使问题规模变大，它仍然相对容易解决。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_137.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_138.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_140.png)

### 增长阶的正式理解

![](img/3faa731ed6e7267f6bdba1ecec8d322c_142.png)

计算机科学家常用“大O符号”描述增长阶，例如 **O(n²)**（读作“阶n平方”）。其含义是：当问题规模 `n` 变得很大时，解决该问题所需的时间**最终**会被某个常数 `K` 乘以 `n²` 的函数**从上界住**。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_144.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_146.png)

更形式化地说：如果我们画出解决问题所需时间相对于问题规模 `n` 的函数图，那么当 `n` 足够大后，这个时间函数曲线将永远位于 `K * n²` 这条曲线的**下方**。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_148.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_149.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_151.png)

增长阶的比较：
*   **O(log n)** （如猜数字）< **O(n)** （线性增长）< **O(n²)** （平方增长）< **O(n³)** （立方增长）< ... < **O(2^n)** （指数增长）

![](img/3faa731ed6e7267f6bdba1ecec8d322c_153.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_155.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_156.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_157.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_159.png)

### 多项式时间与指数时间：关键分水岭

![](img/3faa731ed6e7267f6bdba1ecec8d322c_161.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_162.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_163.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_165.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_167.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_168.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_170.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_171.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_173.png)

在增长阶理论中，最关键的区分是**多项式时间**问题与**指数时间**问题。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_174.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_176.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_177.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_178.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_180.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_181.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_183.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_184.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_186.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_188.png)

*   **多项式时间**：增长阶为 **O(n^k)** 的问题，其中 `k` 是常数（如 O(n), O(n²), O(n¹⁰⁰)）。这类问题即使规模变大，通常也是可处理的。
*   **指数时间**：增长阶为 **O(k^n)** （`k > 1`）的问题（如 O(2^n), O(3^n)）。当问题规模 `n` 增大时，所需时间会爆炸性增长，使得大规模问题在实践上无法解决。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_190.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_192.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_194.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_196.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_197.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_198.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_199.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_201.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_203.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_205.png)

程序员通常希望避免指数时间问题，因为它们无法扩展到工业级规模。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_207.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_208.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_210.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_212.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_214.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_215.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_216.png)

### NP完全问题

![](img/3faa731ed6e7267f6bdba1ecec8d322c_217.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_218.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_219.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_220.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_221.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_223.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_225.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_226.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_227.png)

由此衍生出一个重要概念：**NP完全问题**。这类问题非常有趣：
1.  据我们所知，要**可靠地**找到它们的解，可能需要**指数时间**。
2.  然而，如果某人**猜出**一个解，我们可以在**多项式时间**内**验证**这个解是否正确。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_229.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_230.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_232.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_234.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_235.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_236.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_238.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_239.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_240.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_241.png)

许多实际中有趣的难题（如旅行商问题、部分调度问题）都属于NP完全问题。它们处于可处理与不可处理的边界上。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_243.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_244.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_246.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_248.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_249.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_250.png)

### 并行计算的作用

![](img/3faa731ed6e7267f6bdba1ecec8d322c_252.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_253.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_255.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_256.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_257.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_259.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_260.png)

大脑是一个高度并行的结构，由数十亿神经元同时工作。在计算机科学中，**并行计算**（使用多个处理器或计算机同时解决问题）是减少问题解决时间的有效策略。然而，从理论上看，并行性可以将指数时间缩短，但**不能**将一个本质上是指数时间的问题转变为多项式时间问题。多项式与指数之间的根本区别依然至关重要。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_261.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_262.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_263.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_265.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_267.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_269.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_270.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_271.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_272.png)

## 总结

![](img/3faa731ed6e7267f6bdba1ecec8d322c_274.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_275.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_277.png)

本节课中，我们一起学习了问题困难的多种原因：
1.  **因不确定性而困难**：涉及未来预测、过去推断或需要实时判断的问题，其答案常带有概率性或置信度。
2.  **对人类简单但形式化困难的问题**：如视觉和语言学习，其某些形式化定义已被证明不可能，但我们通过启发式方法能有效解决。
3.  **衡量难度随规模变化：增长阶**：我们引入了 **大O符号**（如 O(n²)）来描述问题难度如何随规模增长。理解了**对数级**、**多项式级**和**指数级**增长的区别，其中**多项式时间与指数时间**的分野是计算机科学中的关键概念。
4.  **相关概念**：简要了解了**NP完全问题**的特点以及**并行计算**的潜力和局限。

![](img/3faa731ed6e7267f6bdba1ecec8d322c_279.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_280.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_281.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_282.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_284.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_285.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_286.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_288.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_290.png)

![](img/3faa731ed6e7267f6bdba1ecec8d322c_291.png)

理解问题的“困难”所在以及如何形式化地衡量这种困难，是连接心智研究与人工智能设计的重要桥梁。在接下来的讨论中，我们将继续探讨其他关于心智与机器问题难度的思考方式。