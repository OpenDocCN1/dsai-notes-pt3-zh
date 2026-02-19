# 课程 45：图数据库 (3/3) 🗺️

![](img/7c112abc71975ecc04d12bce82463725_1.png)

在本节课中，我们将学习图数据库的物理架构、存储机制，并介绍另一种重要的图数据库范式——三元组存储（Triple Stores）及其相关标准 RDF。

![](img/7c112abc71975ecc04d12bce82463725_3.png)

![](img/7c112abc71975ecc04d12bce82463725_4.png)

![](img/7c112abc71975ecc04d12bce82463725_5.png)

![](img/7c112abc71975ecc04d12bce82463725_6.png)

![](img/7c112abc71975ecc04d12bce82463725_7.png)

## 物理架构：复制与分片

上一节我们介绍了图数据库的逻辑模型和查询语言。本节中，我们来看看图数据库在物理上是如何组织和扩展的。

首先，与 MongoDB 类似，图数据库也采用**复制**机制。早期版本的 Neo4j 没有分片功能，只有多个服务器复制整个图的数据。这样做可以实现读取负载均衡，多个读取请求可以分散到所有机器上。

对于写入操作，通常有一个主节点负责处理更新，然后将更改传播到其他副本。后来，系统也允许在所有副本上写入，但这会引入 CAP 定理相关的复杂性问题。

![](img/7c112abc71975ecc04d12bce82463725_9.png)

![](img/7c112abc71975ecc04d12bce82463725_11.png)

![](img/7c112abc71975ecc04d12bce82463725_13.png)

**公式表示复制**：
```
数据副本数 > 1
主节点写入 -> 传播到副本节点
```

![](img/7c112abc71975ecc04d12bce82463725_15.png)

![](img/7c112abc71975ecc04d12bce82463725_17.png)

![](img/7c112abc71975ecc04d12bce82463725_18.png)

---

![](img/7c112abc71975ecc04d12bce82463725_19.png)

![](img/7c112abc71975ecc04d12bce82463725_20.png)

![](img/7c112abc71975ecc04d12bce82463725_21.png)

![](img/7c112abc71975ecc04d12bce82463725_23.png)

接下来是**分片**。分片曾经是图数据库领域的一个难题，但近年来已经得到解决。Oracle 团队的 PGX（分布式版本 PGXD）是首批成功实现图分片的系统之一。

![](img/7c112abc71975ecc04d12bce82463725_25.png)

![](img/7c112abc71975ecc04d12bce82463725_26.png)

![](img/7c112abc71975ecc04d12bce82463725_27.png)

![](img/7c112abc71975ecc04d12bce82463725_28.png)

![](img/7c112abc71975ecc04d12bce82463725_29.png)

![](img/7c112abc71975ecc04d12bce82463725_31.png)

分片的难点在于需要高效地遍历图中的路径。解决方法不是像表或树那样进行严格不重叠的分区，而是允许分区之间存在**重叠**。当遍历图时，如果路径到达另一个分区的数据，查询可以“跳转”到另一台机器上继续执行。这类似于将鼠标移动到屏幕边缘时，光标会移动到另一台电脑屏幕的效果。分片策略高度依赖于查询模式，非常复杂，但如今 Neo4j 等主流图数据库都已支持分片。

![](img/7c112abc71975ecc04d12bce82463725_33.png)

**代码表示分片跳转逻辑**：
```python
# 伪代码：遍历时处理跨分片跳转
def traverse_graph(start_node, query_pattern):
    current_machine = locate_shard(start_node)
    result = []
    for path in explore(current_machine, start_node, query_pattern):
        if path.end_node in another_shard:
            # 跳转到另一个分片机器继续遍历
            switch_to_machine(locate_shard(path.end_node))
            continue_exploration(path.end_node, query_pattern)
        result.append(path)
    return result
```

![](img/7c112abc71975ecc04d12bce82463725_35.png)

![](img/7c112abc71975ecc04d12bce82463725_36.png)

![](img/7c112abc71975ecc04d12bce82463725_37.png)

---

![](img/7c112abc71975ecc04d12bce82463725_39.png)

![](img/7c112abc71975ecc04d12bce82463725_40.png)

![](img/7c112abc71975ecc04d12bce82463725_41.png)

## 物理存储：内存与磁盘

![](img/7c112abc71975ecc04d12bce82463725_43.png)

![](img/7c112abc71975ecc04d12bce82463725_44.png)

![](img/7c112abc71975ecc04d12bce82463725_45.png)

![](img/7c112abc71975ecc04d12bce82463725_46.png)

![](img/7c112abc71975ecc04d12bce82463725_47.png)

![](img/7c112abc71975ecc04d12bce82463725_49.png)

现在，我们来探讨图数据在内存和磁盘上是如何存储的。

![](img/7c112abc71975ecc04d12bce82463725_51.png)

![](img/7c112abc71975ecc04d12bce82463725_53.png)

在**内存**中，图数据库利用 **“索引无关邻接”** 特性。这意味着标签属性图中的节点和边在内存中通过指针直接连接，类似于面向对象编程中对象相互引用的复杂内存结构。这种结构使得遍历边的操作非常高效。

**公式表示内存中的指针关系**：
```
节点A -(指针)-> 边1 -(指针)-> 节点B
```

当需要将数据持久化存储到**磁盘**时，系统会将各个组件分开存储。以下是存储文件的分类：

*   **节点存储**：存储所有节点。
*   **关系存储**：存储所有边（关系）。
*   **属性存储**：存储节点和边的属性值（原子值）。
*   **标签存储**：存储节点的标签。
*   **动态字符串/数组存储**：由于长度可变，字符串和数组被单独处理。

这种存储方式非常模块化。当从磁盘加载数据时，系统会重建内存中的图结构；当持久化时，又将内存结构写回这些独立的文件中。

![](img/7c112abc71975ecc04d12bce82463725_55.png)

在内存中，数据结构被优化以支持快速遍历。例如，一个节点的多个标签以链表形式存储。从一个节点出发的所有边和指向该节点的所有边，分别通过双向链表进行组织，这使得可以高效地迭代所有可能的路径方向。这些底层结构是执行 Cypher 查询模式匹配的基础。

![](img/7c112abc71975ecc04d12bce82463725_57.png)

![](img/7c112abc71975ecc04d12bce82463725_58.png)

![](img/7c112abc71975ecc04d12bce82463725_60.png)

此外，还可以在之上建立索引结构（如哈希或树索引），以加速查找具有特定属性的节点，无需搜索整个图。

---

![](img/7c112abc71975ecc04d12bce82463725_62.png)

![](img/7c112abc71975ecc04d12bce82463725_64.png)

## 图查询语言的标准化 🎯

关于 Neo4j，最后要分享一个非常好的消息：图查询语言正在走向标准化。

![](img/7c112abc71975ecc04d12bce82463725_66.png)

![](img/7c112abc71975ecc04d12bce82463725_67.png)

![](img/7c112abc71975ecc04d12bce82463725_69.png)

![](img/7c112abc71975ecc04d12bce82463725_71.png)

目前有两个重要的标准脱颖而出：
1.  **GQL**：这本质上是 **Cypher 的标准化版本**。多个行业参与者达成协议，协调各自的查询语言，其中大量内容来源于 Cypher。Neo4j 已宣布将逐步演进 Cypher 以对齐该标准。
    > **注意**：不要与 GraphQL 混淆。GraphQL 用于查询树状数据（是众多树查询语言之一），与图数据库无关。
2.  **SQL/PGQ**：这是 **SQL 的扩展**。它在已知的 SQL 语言基础上，增加了图模式匹配功能（即 ASCII 艺术的核心）。这适用于仍处于关系数据库环境但又需要处理图数据的用户。可以预期，像 PostgreSQL 或 MySQL 这样的关系型数据库管理系统将开始支持图类型和相关的 SQL 扩展。

行业标准化的出现令人欣喜，这意味着所有行业参与者可以聚焦并对齐到统一的标准上。

![](img/7c112abc71975ecc04d12bce82463725_73.png)

![](img/7c112abc71975ecc04d12bce82463725_75.png)

> **关于考试语言的说明**：在考试中，你们只需要掌握四种语言：PostgreSQL 的 SQL、PySpark API、Spark SQL 和 JSONiq。对于其他如 MongoDB、Cypher 等，只会涉及理论性问题或代码理解，不需要编写代码。

![](img/7c112abc71975ecc04d12bce82463725_77.png)

![](img/7c112abc71975ecc04d12bce82463725_78.png)

![](img/7c112abc71975ecc04d12bce82463725_79.png)

---

## 第二种范式：三元组存储与 RDF

![](img/7c112abc71975ecc04d12bce82463725_81.png)

![](img/7c112abc71975ecc04d12bce82463725_83.png)

![](img/7c112abc71975ecc04d12bce82463725_84.png)

现在，我们转向图数据库的第二种范式：**三元组存储**，其标准是 **RDF**（万维网联盟 W3C 标准）。

![](img/7c112abc71975ecc04d12bce82463725_86.png)

![](img/7c112abc71975ecc04d12bce82463725_87.png)

![](img/7c112abc71975ecc04d12bce82463725_88.png)

![](img/7c112abc71975ecc04d12bce82463725_90.png)

![](img/7c112abc71975ecc04d12bce82463725_91.png)

三元组存储的核心思想是比标签属性图更加**细粒度**。在标签属性图中，一个节点可能拥有多个属性。而在三元组存储中，每个属性都被分解成一个独立的边和节点。因此，三元组存储只包含**节点、边以及边上的标签**。

![](img/7c112abc71975ecc04d12bce82463725_93.png)

之所以称为“三元组”存储，是因为其中的所有数据都表示为 **（主体，属性，客体）** 的形式，类似于英语中的“主-谓-宾”句子（例如，“ETH 位于 瑞士”）。整个数据库就是一个庞大的三元组列表，这些三元组共同构成了一个图。

**公式表示三元组**：
```
三元组 = (主体, 属性, 客体)
```

---

![](img/7c112abc71975ecc04d12bce82463725_95.png)

### RDF 数据模型

![](img/7c112abc71975ecc04d12bce82463725_97.png)

![](img/7c112abc71975ecc04d12bce82463725_99.png)

在 RDF 中，节点和边的命名有三种方式：

![](img/7c112abc71975ecc04d12bce82463725_101.png)

以下是节点和边标识的规则：
*   **主体**：可以是 URI 或空白节点，不能是字面量。
*   **属性**：必须是 URI。
*   **客体**：可以是 URI、空白节点或字面量。

![](img/7c112abc71975ecc04d12bce82463725_103.png)

---

### RDF 语法

![](img/7c112abc71975ecc04d12bce82463725_105.png)

![](img/7c112abc71975ecc04d12bce82463725_106.png)

与树（XML、JSON）和表（CSV）一样，RDF 也有多种语法来表示三元组列表，它们遵循相同的模型。

![](img/7c112abc71975ecc04d12bce82463725_108.png)

![](img/7c112abc71975ecc04d12bce82463725_109.png)

![](img/7c112abc71975ecc04d12bce82463725_110.png)

![](img/7c112abc71975ecc04d12bce82463725_111.png)

![](img/7c112abc71975ecc04d12bce82463725_112.png)

![](img/7c112abc71975ecc04d12bce82463725_114.png)

![](img/7c112abc71975ecc04d12bce82463725_116.png)

1.  **Turtle**：最流行的语法。在文件中每行一个三元组。可以使用前缀（`@prefix`）和分号`;`、逗号`,`来简化重复的主体或属性书写。
2.  **JSON-LD**：JSON 格式的语法。将具有相同主体的所有属性-客体对组织在一个 JSON 对象中。
3.  **RDF/XML**：XML 格式的语法。

![](img/7c112abc71975ecc04d12bce82463725_118.png)

![](img/7c112abc71975ecc04d12bce82463725_120.png)

对于三元组存储，当看到 `geo:locatedIn` 这样的 QName 时，会将其前缀和本地部分拼接成一个完整的 URI（例如，`http://example.com/geography#locatedIn`）。

![](img/7c112abc71975ecc04d12bce82463725_122.png)

---

### 查询语言：SPARQL

三元组存储的查询语言是 **SPARQL**（不要与 Spark SQL 混淆）。SPARQL 用于查询 RDF 数据。

![](img/7c112abc71975ecc04d12bce82463725_124.png)

SPARQL 也使用子句结构，类似于 SQL。它的核心是**图模式匹配**，功能上类似于 Cypher 的 ASCII 艺术模式。例如，查询“所有位于瑞士的东西”或“所有位于美洲的国家内的学校”。

**代码表示 SPARQL 查询示例**：
```sparql
# 查找所有位于瑞士的事物
PREFIX geo: <http://example.com/geography#>
SELECT ?thing
WHERE {
    ?thing geo:locatedIn <http://example.com/Switzerland> .
}

# 查找所有位于美洲国家内的学校
PREFIX geo: <http://example.com/geography#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
SELECT ?school
WHERE {
    ?school rdf:type <http://example.com/School> .
    ?school geo:locatedIn ?country .
    ?country geo:locatedIn <http://example.com/America> .
}
```

---

### RDF 与知识图谱、人工智能

RDF 和三元组存储的一个重要应用领域是构建**知识图谱**和**人工智能**。

![](img/7c112abc71975ecc04d12bce82463725_126.png)

![](img/7c112abc71975ecc04d12bce82463725_127.png)

![](img/7c112abc71975ecc04d12bce82463725_129.png)

![](img/7c112abc71975ecc04d12bce82463725_131.png)

在机器学习盛行之前，人工智能的另一种方法是基于知识库和逻辑推理。RDF 三元组可以作为形式化的知识片段。通过在其上定义**本体**——即类（如国家、人物）和属性（如位于、人口）的正式规范，可以对存储的知识进行**推理**。

例如，通过“所有人都是会死的”和“苏格拉底是人”这两个三元组，系统可以推理出“苏格拉底是会死的”。这种基于符号逻辑的推理仍然是人工智能中一个重要且活跃的研究方向，与当前流行的语言模型形成互补。

在 RDF 之上定义本体和推理规则的层被称为 **OWL**。

---

![](img/7c112abc71975ecc04d12bce82463725_133.png)

![](img/7c112abc71975ecc04d12bce82463725_134.png)

![](img/7c112abc71975ecc04d12bce82463725_135.png)

![](img/7c112abc71975ecc04d12bce82463725_136.png)

![](img/7c112abc71975ecc04d12bce82463725_137.png)

## 总结

![](img/7c112abc71975ecc04d12bce82463725_138.png)

![](img/7c112abc71975ecc04d12bce82463725_140.png)

![](img/7c112abc71975ecc04d12bce82463725_141.png)

![](img/7c112abc71975ecc04d12bce82463725_142.png)

![](img/7c112abc71975ecc04d12bce82463725_143.png)

![](img/7c112abc71975ecc04d12bce82463725_144.png)

![](img/7c112abc71975ecc04d12bce82463725_145.png)

![](img/7c112abc71975ecc04d12bce82463725_146.png)

![](img/7c112abc71975ecc04d12bce82463725_147.png)

本节课中我们一起学习了：
1.  **图数据库的物理架构**，包括通过复制实现高可用和读扩展，以及通过允许重叠的复杂分片策略实现写扩展。
2.  **图数据的物理存储**，了解了“索引无关邻接”在内存中的高效指针结构，以及节点、边、属性等组件在磁盘上分离存储的模块化方式。
3.  **图查询语言的标准化进展**，介绍了 GQL（基于 Cypher）和 SQL/PGQ（SQL 的图扩展）两大标准。
4.  **图数据库的第二种范式——三元组存储**，深入探讨了 RDF 数据模型（主体-属性-客体）、多种语法（Turtle, JSON-LD, RDF/XML）以及查询语言 SPARQL。
5.  **RDF 在知识图谱和人工智能中的应用**，了解了其作为形式化知识库支持逻辑推理的作用。

![](img/7c112abc71975ecc04d12bce82463725_148.png)

![](img/7c112abc71975ecc04d12bce82463725_149.png)

![](img/7c112abc71975ecc04d12bce82463725_150.png)

![](img/7c112abc71975ecc04d12bce82463725_151.png)

![](img/7c112abc71975ecc04d12bce82463725_152.png)

![](img/7c112abc71975ecc04d12bce82463725_153.png)

![](img/7c112abc71975ecc04d12bce82463725_154.png)

![](img/7c112abc71975ecc04d12bce82463725_156.png)

![](img/7c112abc71975ecc04d12bce82463725_157.png)

我们看到了，除了树和表，图也是一种重要的数据形态，并且同样遵循着数据独立性的理念，拥有自己的语法、查询语言，并正在走向标准化。