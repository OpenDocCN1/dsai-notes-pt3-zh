# 人工智能基础：03：盲目搜索 🧭

![](img/6289a44da8c9032c2ed5f6023ad087af_0.png)

在本节课中，我们将要学习人工智能中的搜索问题，特别是**盲目搜索**策略。我们将介绍几种基本的搜索算法，分析它们的性能，并理解它们在不同场景下的应用。

---

## 概述

搜索是人工智能中的核心问题之一，用于在状态空间中寻找从初始状态到目标状态的路径。本节课我们将重点讨论**盲目搜索**（也称为无信息搜索），这类算法在搜索过程中不利用任何关于目标位置的额外知识。我们将学习广度优先搜索、深度优先搜索、一致代价搜索等经典算法，并通过关键参数（如完备性、最优性、时间和空间复杂度）来评估它们。

---

## 搜索策略的评估参数

在深入具体算法之前，我们首先需要了解用于评估不同搜索策略的几个关键参数。

*   **完备性**：如果问题存在解，该策略是否能保证找到解？
*   **时间复杂性**：找到解需要多少步（或扩展多少个节点）？
*   **空间复杂性**：算法运行需要多少内存来存储状态信息？
*   **最优性**：该策略是否能保证找到代价最小的解？（通常我们默认处理最小化问题）

在分析复杂度时，我们通常关注最坏情况，并使用以下符号：
*   **b**：搜索树的最大分支因子（即一个状态最多能产生的后继状态数）。
*   **d**：最浅解所在的深度（即到达目标所需的最少步数）。
*   **m**：状态空间的最大深度（可能为无穷大）。

一个深度为 `m` 的树，其节点总数上界为 `O(b^m)`。

---

## 广度优先搜索 (BFS) 🌊

上一节我们介绍了评估搜索算法的通用参数，本节中我们来看看第一种具体策略——广度优先搜索。

广度优先搜索的核心思想是：总是扩展**最浅**的未扩展节点。这通过将边界（存储待扩展节点的集合）实现为一个**先进先出队列**来完成。

### 算法流程（图搜索版本）

以下是广度优先搜索图搜索版本的核心伪代码逻辑：

```python
function BFS(problem):
    node = Node(problem.INITIAL_STATE) # 用初始状态创建节点
    if problem.GOAL_TEST(node.state):
        return SOLUTION(node)
    frontier = Queue() # 边界初始化为队列
    frontier.push(node)
    explored = Set() # 已探索集合初始化为空

    while not frontier.isEmpty():
        node = frontier.pop() # 取出队列中最老的节点
        explored.add(node.state) # 标记该状态已探索
        for action in problem.ACTIONS(node.state):
            child = CHILD_NODE(problem, node, action)
            if child.state not in explored and child not in frontier:
                if problem.GOAL_TEST(child.state): # 生成时即检查目标
                    return SOLUTION(child)
                frontier.push(child)
    return FAILURE
```

**关键点**：目标测试在生成子节点后立即进行，而不是在从边界取出时进行，这可以节省一整层的搜索时间。

### BFS的性质分析

以下是广度优先搜索的主要性质：

*   **时间复杂性**：`O(b^d)`。在最坏情况下，需要探索到深度 `d` 的所有节点。
*   **空间复杂性**：`O(b^d)`。边界需要存储一整层的节点，内存消耗巨大。
*   **完备性**：如果分支因子 `b` 有限，则完备。
*   **最优性**：当所有单步代价相同时（即寻找最少步数解），BFS 是最优的。

BFS 的主要缺点是内存需求过高，在处理大规模问题时可能不切实际。

---

## 一致代价搜索 (UCS) ⚖️

上一节我们看到了按“层”搜索的 BFS，本节中我们来看看一种考虑路径代价的搜索策略——一致代价搜索。

一致代价搜索的核心思想是：总是扩展**路径代价最小**的节点。这通过将边界实现为一个按路径代价 `g(n)` 排序的**优先队列**（如最小堆）来完成。它是 BFS 的推广（当所有单步代价相等时，UCS 退化为 BFS）。

### 算法流程与关键区别

UCS 的算法框架与 BFS 类似，但有几个关键区别：

1.  **边界管理**：使用优先队列，按 `g(n)`（从初始节点到节点 `n` 的实际路径代价）排序。
2.  **目标测试时机**：目标测试在节点**从边界中取出**准备扩展时进行，而不是在生成时进行。这是为了确保找到的是最优解。
3.  **代价更新**：如果新发现的到达某个状态的路径代价更低，则需要更新边界中该节点对应的路径代价。

```python
function UCS(problem):
    node = Node(problem.INITIAL_STATE, path_cost=0)
    frontier = PriorityQueue(order_by=path_cost)
    frontier.push(node)
    explored = Set()

    while not frontier.isEmpty():
        node = frontier.pop() # 取出当前路径代价最小的节点
        if problem.GOAL_TEST(node.state): # 取出时进行目标测试
            return SOLUTION(node)
        explored.add(node.state)
        for action in problem.ACTIONS(node.state):
            child = CHILD_NODE(problem, node, action)
            if child.state not in explored:
                if child not in frontier:
                    frontier.push(child)
                else if child in frontier with higher path_cost:
                    replace the frontier node with child # 更新为代价更低的路径
    return FAILURE
```

### UCS的性质分析

以下是一致代价搜索的主要性质：

*   **时间与空间复杂性**：最坏情况下的复杂度可以表示为 `O(b^(1 + ⌊C*/ε⌋))`，其中 `C*` 是最优解的代价，`ε` 是最小的单步代价。这通常比 BFS 的 `O(b^d)` 更差，但 UCS 处理的是代价不均等的问题。
*   **完备性**：如果单步代价均大于某个正数 `ε`，则完备。
*   **最优性**：是。UCS 总能找到代价最小的解。

UCS 是许多更高级搜索算法（如 A* 搜索）的基础框架。

---

## 深度优先搜索 (DFS) 🌲

前面我们讨论了以广度或代价为导向的搜索，本节中我们来看看另一种截然不同的策略——深度优先搜索。

深度优先搜索的核心思想是：总是扩展**最深**的未扩展节点。这通过将边界实现为一个**后进先出栈**来完成。

### 算法特点

DFS 的算法结构与 BFS 几乎相同，只需将队列替换为栈。其探索顺序是沿着一条路径深入到底，直到无法继续，然后回溯。

### DFS的性质分析

以下是深度优先搜索的主要性质：

*   **时间复杂性**：最坏情况下为 `O(b^m)`。如果 `m` 远大于 `d`，且搜索树非常深，这可能比 BFS 差很多。
*   **空间复杂性**：`O(bm)`。只需要存储当前分支上的节点，内存消耗远小于 BFS 和 UCS。这是 DFS 的最大优势。
*   **完备性**：
    *   图搜索版本在有限状态空间中是完备的。
    *   树搜索版本在不含无限深路径或循环的有限状态空间中也是完备的（可通过检查当前路径是否出现重复状态来避免循环）。
*   **最优性**：否。DFS 不保证找到最短路径或最小代价解。

在实际应用中，DFS 常以**回溯搜索**的形式实现，它只生成一个后继节点，并记录状态以在回溯时生成下一个后继，从而进一步节省空间。

---

## 迭代加深搜索 (IDS) 🔄

我们已经看到了 BFS（最优但耗内存）和 DFS（省内存但不完备/非最优）的优缺点。本节中我们来看看如何结合两者优势的一种策略——迭代加深搜索。

迭代加深搜索的核心思想是：重复运行**深度受限搜索**，并逐渐增加深度限制 `l`。深度受限搜索是 DFS，但在达到预设深度 `l` 时会停止并回溯。

### 算法流程

```python
function ITERATIVE_DEEPENING_SEARCH(problem):
    for depth = 0 to INFINITY:
        result = DEPTH_LIMITED_SEARCH(problem, depth)
        if result != CUTOFF: # CUTOFF 表示因深度限制未找到解
            return result

function DEPTH_LIMITED_SEARCH(problem, limit):
    return RECURSIVE_DLS(Node(problem.INITIAL_STATE), problem, limit)

function RECURSIVE_DLS(node, problem, limit):
    if problem.GOAL_TEST(node.state):
        return SOLUTION(node)
    elif limit == 0:
        return CUTOFF
    else:
        cutoff_occurred = False
        for action in problem.ACTIONS(node.state):
            child = CHILD_NODE(problem, node, action)
            result = RECURSIVE_DLS(child, problem, limit - 1)
            if result == CUTOFF:
                cutoff_occurred = True
            elif result != FAILURE:
                return result
        if cutoff_occurred:
            return CUTOFF
        else:
            return FAILURE
```

### IDS的性质分析

以下是迭代加深搜索的主要性质：

*   **时间复杂性**：`O(b^d)`。虽然浅层节点会被重复扩展，但大部分工作集中在最深一层，总时间复杂度和 BFS 同阶。
*   **空间复杂性**：`O(bd)`。与 DFS 相同，只需要存储当前路径上的节点。
*   **完备性**：是。
*   **最优性**：当单步代价相同时，是最优的（能找到最浅解）。

IDS 结合了 BFS 的最优性、完备性和 DFS 的空间效率，是处理状态空间大、解深度未知问题时的实用选择。

---

## 搜索策略对比与补充

本节课我们一起学习了多种盲目搜索策略，以下是它们的总结对比：

| 策略 | 边界数据结构 | 时间复杂性 | 空间复杂性 | 完备性？ | 最优性？ | 备注 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 广度优先搜索 | 队列 | `O(b^d)` | `O(b^d)` | 是 | 是（步数） | 内存消耗大 |
| 一致代价搜索 | 优先队列 (`g(n)`) | `O(b^(1+⌊C*/ε⌋))` | `O(b^(1+⌊C*/ε⌋))` | 是 | 是（代价） | 代价不均等问题的基础算法 |
| 深度优先搜索 | 栈 | `O(b^m)` | `O(bm)` | 有限状态空间是 | 否 | 内存效率高，常以回溯形式实现 |
| 深度受限搜索 | 栈 | `O(b^l)` | `O(bl)` | 否（若 `d > l`） | 否 | IDS 的组件 |
| 迭代加深搜索 | 栈（多次调用） | `O(b^d)` | `O(bd)` | 是 | 是（步数） | 结合 BFS 和 DFS 的优点 |

### 其他搜索变体

*   **双向搜索**：同时从初始状态和目标状态开始搜索，直到两个搜索 frontier 相遇。理想情况下，时间复杂性可从 `O(b^d)` 降为 `O(b^(d/2))`。
*   **搜索方向**：除了前向搜索，也可以进行**后向搜索**（从目标状态反向推理），适用于某些特定问题。

在实际应用中，BFS 和 UCS 通常使用**图搜索**版本以避免重复探索，而 DFS 和 IDS 通常使用**树搜索**版本以保持其空间效率优势。现代实现也常使用**缓存**技术来平衡时间和空间开销。

---

## 总结

![](img/6289a44da8c9032c2ed5f6023ad087af_2.png)

![](img/6289a44da8c9032c2ed5f6023ad087af_3.png)

本节课中我们一起学习了人工智能中的盲目搜索策略。我们从评估搜索算法的通用参数开始，依次深入探讨了广度优先搜索、一致代价搜索、深度优先搜索以及结合两者优点的迭代加深搜索。我们分析了每种算法的时间、空间复杂度、完备性和最优性，并理解了它们各自的适用场景。盲目搜索是更高级的**启发式搜索**的基础，在下一节课中，我们将学习如何利用问题领域的知识来引导搜索，从而更高效地解决问题。