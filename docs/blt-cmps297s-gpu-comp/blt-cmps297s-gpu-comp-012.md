# GPU计算：第12讲：扫描（Brent-Kung算法） 🚀

在本节课中，我们将学习一种不同于上次讨论的并行扫描算法——Brent-Kung并行扫描算法。我们还将探讨线程粗化在扫描中的应用，以提升算法的工作效率。

## 概述 📋

上一讲我们介绍了扫描模式，并重点讲解了用于并行扫描的Kogge-Stone方法及其优化技术——双缓冲。扫描模式是指，给定一个数组，输出数组的每个元素将是其前面所有元素的组合（对于包含性扫描，还包括当前元素；对于排他性扫描，则不包括）。我们以加法为例，但该模式同样适用于其他满足结合律的操作符，如乘法、最小值、最大值等。

为了实现并行扫描，我们像处理归约一样对输入进行分段。这是因为并行扫描需要同步，而不同线程块之间无法实现同步。因此，我们将输入分段，每个线程块扫描自己的段，将部分和存储在一个子数组中，然后扫描这个部分和数组。最后，每个线程块将扫描后的部分和（来自其前面的块）加到其内部元素上，从而得到最终的全局扫描数组。

我们用于单个线程块内扫描的算法是Kogge-Stone并行算法。该算法让每个线程加上与其相距特定步长的元素，步长从1开始，每次翻倍，直到覆盖整个数组。由于存在读写冲突，我们需要在读和写之间进行同步。为了减少同步开销，我们引入了双缓冲技术，即使用输入缓冲区和输出缓冲区，并在每次迭代后交换它们。

我们还分析了Kogge-Stone算法的工作效率。虽然顺序扫描执行n次加法，但Kogge-Stone方法在log n步中，每步执行n - 2^步长 次操作，总计约O(n log n)次操作。这表明该算法的工作效率不高，因为它比顺序算法执行了更多冗余操作。如果线程块因资源有限而被串行化，这种低工作效率可能会影响性能。

因此，本节课我们将探讨Brent-Kung扫描算法，并学习如何应用线程粗化来优化扫描。

## Brent-Kung并行扫描算法 🔄

Brent-Kung并行包含性扫描算法分为两个主要步骤。

### 第一步：归约阶段

第一步类似于一个归约树。我们首先将相邻的两个元素相加。在这个阶段，我们为每两个元素分配一个线程，因为每一步的加法操作数量在减少。接着，我们将相距两个步长的元素相加，然后是相距四个步长的元素，依此类推，直到完成整个数组的归约树。这个阶段被称为归约阶段。

### 第二步：后归约阶段

完成归约阶段后，数组中部分扫描值已经就绪，但其他值尚未完成。例如，x4和x5的和缺少x0到x3的部分。在第二阶段，我们将完成这些剩余值的计算。我们通过将左侧相距一个步长的值相加来完成扫描。例如，将x0到x3加到x4和x5上，得到x0到x5的和。类似地，我们将x0和x1加到x2上，得到x0到x2的和，以此类推。这个阶段被称为后归约阶段。

### 算法对比与分析

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_1.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_3.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_5.png)

以下是Kogge-Stone算法与Brent-Kung算法的对比：

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_7.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_8.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_10.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_11.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_12.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_13.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_15.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_16.png)

*   **Kogge-Stone算法**：步数少（log n步），但总操作数多（O(n log n)）。
*   **Brent-Kung算法**：步数多（2 log n - 1步），但总操作数少（O(n)次操作），因此具有更高的工作效率。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_18.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_20.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_22.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_24.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_26.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_27.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_29.png)

具体分析如下：
*   **归约阶段**：执行log n步，操作数为n - 1。
*   **后归约阶段**：执行log n - 1步，操作数为n - 2 log n - 1。
*   **总计**：步数为2 log n - 1，操作数为2n - log n - 2，即O(n)次操作。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_31.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_33.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_35.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_37.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_38.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_39.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_40.png)

因此，Brent-Kung算法虽然步骤更多，但更高效。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_42.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_43.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_45.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_47.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_49.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_51.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_53.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_55.png)

## 算法实现与优化 ⚙️

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_57.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_58.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_60.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_61.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_63.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_64.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_66.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_67.png)

在实现Brent-Kung算法时，我们应用了共享内存和线程重索引等优化技术。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_69.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_71.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_73.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_75.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_77.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_78.png)

### 共享内存的使用

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_80.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_81.png)

与Kogge-Stone算法类似，使用共享内存可以提高数据重用性。此外，对于Brent-Kung算法，全局内存访问可能无法合并，而使用共享内存可以确保全局内存加载是合并的，从而进一步提升性能。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_83.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_84.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_86.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_88.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_90.png)

### 双缓冲的必要性

在Kogge-Stone算法中，由于同一迭代中有线程读写同一内存位置，我们需要双缓冲来避免冲突。然而，在Brent-Kung算法中，同一迭代中没有线程同时读写同一数据元素，因此不需要双缓冲，可以使用单个缓冲区。

### 控制流分歧与线程重索引

在Kogge-Stone算法中，控制流分歧不是问题，因为每一步中活跃的线程是连续的。但在Brent-Kung算法中，如果为每个输入值分配一个线程，会导致严重的控制流分歧，因为并非所有输入值在每一步都被处理。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_92.png)

为了避免控制流分歧，我们采用线程重索引技术。我们不再为每个线程固定分配特定的数据元素，而是在每次迭代中根据步长重新分配线程负责的数据元素，确保活跃的线程尽可能连续，从而最大化线程束的执行效率。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_94.png)

线程重索引的关键是计算每个线程在给定步长下负责的数据元素索引。我们推导出索引公式为：
`index = (thread_idx + 1) * 2 * stride - 1`
其中，`thread_idx`是线程索引，`stride`是当前步长。在实现时，需要确保索引在数组边界内。

### 排他性扫描的实现

对于排他性扫描，有两种实现方式：
1.  将其表述为包含性扫描，即将输入元素左移一位。
2.  修改Brent-Kung算法的后归约阶段，专门实现排他性扫描。

第二种方法通过巧妙地移动和添加元素，在归约阶段后，将最后一个元素（全段和）保存为块的部分和并替换为零，然后在后归约阶段通过一系列操作将零和部分和移动到正确位置，最终得到排他性扫描结果。这种方法在作业中需要实现。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_96.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_98.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_100.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_102.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_103.png)

## 线程粗化优化 🧵

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_105.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_107.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_109.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_111.png)

线程粗化是一种优化技术，用于在过度并行化导致工作效率下降时，减少性能损失。在扫描的上下文中，我们可以通过分段扫描应用线程粗化。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_113.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_115.png)

具体方法是：在每个线程块内，让每个线程顺序扫描一个子段（例如8个元素），产生该子段的部分和。然后，线程块并行扫描这些线程部分和数组。最后，每个线程将对应的扫描部分和（来自前面的线程）加到其子段的元素上。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_117.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_118.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_120.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_121.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_123.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_125.png)

这样，我们利用顺序扫描的高工作效率处理子段，仅对部分和进行并行扫描，从而在保持并行性的同时提高了整体算法的工作效率。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_127.png)

以下是应用线程粗化后的性能对比示例：
*   未使用线程粗化：约4.5毫秒
*   使用线程粗化（因子为8）：约1.5毫秒
性能提升了约3倍。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_129.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_130.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_131.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_133.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_135.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_137.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_138.png)

## 总结 📝

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_140.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_142.png)

本节课我们一起学习了Brent-Kung并行扫描算法。该算法通过归约和后归约两个阶段，以更多的步数换取了更少的操作总数，从而实现了更高的工作效率。我们探讨了其实现中的关键优化技术，包括共享内存的使用和线程重索引以避免控制流分歧。同时，我们分析了排他性扫描的两种实现方式。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_144.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_146.png)

最后，我们介绍了线程粗化优化技术，它通过让线程顺序处理数据子段来减少并行算法带来的工作效率损失，并在实际代码中展示了显著的性能提升。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_148.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_150.png)

通过对比Kogge-Stone和Brent-Kung算法，我们理解了在并行计算中工作效率与并行度之间的权衡，以及根据具体硬件和问题规模选择合适算法的重要性。