# 22：数据模型 (2/4) 🌳

在本节课中，我们将学习如何将JSON和XML文档视为树形结构，理解它们在内存中的表示方式，并初步了解数据验证（Validation）和模式（Schema）的概念。

![](img/17f4d5d915cb83e727719ecd4bbdff22_1.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_2.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_3.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_4.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_5.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_6.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_7.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_9.png)

---

![](img/17f4d5d915cb83e727719ecd4bbdff22_11.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_13.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_14.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_16.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_18.png)

## 从JSON/XML语法到内存中的树

![](img/17f4d5d915cb83e727719ecd4bbdff22_20.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_21.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_22.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_23.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_24.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_25.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_27.png)

上一节我们介绍了JSON和XML的基本语法。本节中我们来看看这些语法结构在计算机内存中是如何表示的。

![](img/17f4d5d915cb83e727719ecd4bbdff22_29.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_30.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_31.png)

当我们处理一个JSON或XML文件时，第一步通常是使用解析器（Parser）将其读入内存。解析器会根据语法规则分析文本，但它在内存中构建的并不是文本本身，而是一个**树形结构**。

![](img/17f4d5d915cb83e727719ecd4bbdff22_33.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_34.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_35.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_36.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_37.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_38.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_39.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_40.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_42.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_44.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_45.png)

### 将JSON对象可视化为树

![](img/17f4d5d915cb83e727719ecd4bbdff22_47.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_49.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_51.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_53.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_54.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_56.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_57.png)

让我们通过一个具体的JSON例子来理解这个过程。

![](img/17f4d5d915cb83e727719ecd4bbdff22_59.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_60.png)

```json
{
  "foo": true,
  "bar": [{"a": 1}, null]
}
```

![](img/17f4d5d915cb83e727719ecd4bbdff22_62.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_64.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_66.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_67.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_68.png)

这个JSON对象可以转化为以下树形结构：

![](img/17f4d5d915cb83e727719ecd4bbdff22_70.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_71.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_73.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_74.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_75.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_76.png)

*   **根节点**是一个对象（用紫色矩形表示）。
*   这个对象有两条边（箭头）指向它的值：
    *   标签为 `"foo"` 的边指向一个原子值 `true`（用黄色矩形表示）。
    *   标签为 `"bar"` 的边指向一个数组（用红色矩形表示）。
*   这个数组包含两个元素：
    *   第一个元素是一个对象（紫色），它有一条标签为 `"a"` 的边指向原子值 `1`。
    *   第二个元素是原子值 `null`（黄色）。

![](img/17f4d5d915cb83e727719ecd4bbdff22_77.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_78.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_79.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_80.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_81.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_82.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_84.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_85.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_86.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_88.png)

**核心概念**：在JSON的树模型中，**键（Key）是边的标签**，而节点（矩形）代表值（对象、数组或原子值）。这是一个有根树，箭头从父节点指向子节点。

![](img/17f4d5d915cb83e727719ecd4bbdff22_89.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_90.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_92.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_94.png)

### 将XML文档可视化为树

![](img/17f4d5d915cb83e727719ecd4bbdff22_96.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_97.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_99.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_101.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_103.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_104.png)

XML文档同样可以转化为树。例如下面这个XML：

![](img/17f4d5d915cb83e727719ecd4bbdff22_106.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_107.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_109.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_110.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_112.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_114.png)

```xml
<?xml version="1.0"?>
<metadata>
  <title lang="en" year="2022">Sys. Group</title>
  <publisher>ETH Zurich</publisher>
</metadata>
```

![](img/17f4d5d915cb83e727719ecd4bbdff22_116.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_117.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_118.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_119.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_120.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_122.png)

其对应的树形结构如下：

![](img/17f4d5d915cb83e727719ecd4bbdff22_124.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_126.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_127.png)

*   **根节点**是一个文档节点。
*   文档节点的子节点是 `<metadata>` 元素节点。
*   `<metadata>` 有两个子元素节点：`<title>` 和 `<publisher>`。
*   `<title>` 节点：
    *   拥有属性节点 `lang="en"` 和 `year="2022"`。
    *   拥有一个文本子节点，内容为 `"Sys. Group"`。
*   `<publisher>` 节点拥有一个文本子节点，内容为 `"ETH Zurich"`。

![](img/17f4d5d915cb83e727719ecd4bbdff22_129.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_130.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_131.png)

**核心概念**：在XML的树模型（如XML信息集）中，**元素名和属性名是节点本身的属性**，而不是边的标签。这与JSON模型的一个关键区别。

---

## 解析与序列化 🔄

理解了树形结构后，我们需要两个重要的动词来描述数据在磁盘和内存之间的转换过程。

以下是这两个过程的核心描述：

![](img/17f4d5d915cb83e727719ecd4bbdff22_133.png)

*   **解析 (Parsing)**：将磁盘上的JSON/XML文本语法，通过解析器读入内存，构建成树形结构的过程。
    *   公式表示：`文本语法 -(解析)-> 内存中的树`
*   **序列化 (Serializing)**：将内存中的树形结构转换回JSON/XML文本语法，并写入磁盘或网络的过程。
    *   公式表示：`内存中的树 -(序列化)-> 文本语法`

![](img/17f4d5d915cb83e727719ecd4bbdff22_135.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_136.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_138.png)

**重要认识**：程序在内存中处理数据时，操作的是树节点及其关系，而非原始的文本字符串。语法只是用于交换和存储的格式。

![](img/17f4d5d915cb83e727719ecd4bbdff22_140.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_142.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_143.png)

---

## 正式的数据模型：XML信息集示例

![](img/17f4d5d915cb83e727719ecd4bbdff22_145.png)

为了精确地在内存中表示XML文档，W3C制定了 **XML信息集（XML Infoset）** 标准。它定义了树中可能出现的节点类型、它们的属性以及访问方法。

![](img/17f4d5d915cb83e727719ecd4bbdff22_147.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_149.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_151.png)

我们主要关注以下四种节点类型：
1.  **文档信息项**：代表整个文档。
2.  **元素信息项**：代表XML元素。
3.  **属性信息项**：代表元素的属性。
4.  **字符信息项**：代表元素或属性内的文本内容。

![](img/17f4d5d915cb83e727719ecd4bbdff22_153.png)

每个信息项都有其属性。例如，一个“元素信息项”可能拥有以下属性：
*   `local name`：元素名称（如 `"title"`）。
*   `children`：子节点列表。
*   `attributes`：属性节点列表。
*   `parent`：指向父节点的引用。

![](img/17f4d5d915cb83e727719ecd4bbdff22_155.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_157.png)

这些属性（如 `parent` 和 `children`）定义了树中的边，使我们能够在节点间双向导航。这种正式的定义是构建查询语言的基础。

![](img/17f4d5d915cb83e727719ecd4bbdff22_159.png)

---

## 良构性与验证 ✅

处理文档时，有两个层次的质量检查：

![](img/17f4d5d915cb83e727719ecd4bbdff22_161.png)

1.  **良构性 (Well-formedness)**：这是一个“是/否”问题。检查文档是否符合JSON/XML的基本语法规则（如标签闭合、引号匹配）。如果文档不是良构的，解析器将报错并无法构建树。
    *   **公式表示**：`文档 -(解析器)-> 成功构建树？ (是/否)`

![](img/17f4d5d915cb83e727719ecd4bbdff22_163.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_164.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_165.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_166.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_168.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_169.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_171.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_172.png)

2.  **验证 (Validation)**：在文档良构的基础上，进一步检查其结构是否符合某个特定的**模式（Schema）**。模式定义了数据应遵循的约束，例如：
    *   “`person` 对象必须包含 `age` 字段，且其值必须为数字。”
    *   “`title` 元素必须包含 `lang` 属性。”
    *   **公式表示**：`内存中的树 -(依据模式Schema检查)-> 有效？ (是/否)`

![](img/17f4d5d915cb83e727719ecd4bbdff22_174.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_175.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_176.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_178.png)

**验证的附加作用：注解 (Annotation)**
验证过程常常伴随“注解”。例如，模式可能规定某个字段必须是整数。验证器在确认文本 `"42"` 符合整数格式后，可以将内存中对应的文本节点“注解”或转换为一个真正的整数类型节点，从而提升后续数值运算的效率。

![](img/17f4d5d915cb83e727719ecd4bbdff22_180.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_182.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_183.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_185.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_187.png)

---

![](img/17f4d5d915cb83e727719ecd4bbdff22_189.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_190.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_192.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_194.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_196.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_197.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_198.png)

## 模式与数据集合

![](img/17f4d5d915cb83e727719ecd4bbdff22_199.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_200.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_201.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_203.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_204.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_206.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_207.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_208.png)

在“大数据”场景中，我们通常处理的是海量文档的集合。

![](img/17f4d5d915cb83e727719ecd4bbdff22_210.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_211.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_212.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_213.png)

*   **无模式的异构集合**：集合中的文档结构各异。这提供了灵活性，适合处理历史日志等自然演变的数据，但可能牺牲一定的处理性能。
*   **有模式的同构集合**：所有文档都通过同一个模式进行验证。这确保了数据结构的一致性。
    *   **优势**：同质化的数据允许系统使用更高效的内存布局和存储格式（如列式存储），从而大幅提升查询和分析性能。
    *   **权衡**：写入数据时需要额外的验证开销，但读取性能会得到优化。这是一种典型的“空间/时间”或“写/读”权衡。

![](img/17f4d5d915cb83e727719ecd4bbdff22_215.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_217.png)

模式语言（如JSON Schema, XML Schema）允许我们定义丰富的约束，从简单的类型检查（“必须是字符串”）到复杂的结构断言（“数组的第一个元素是对象，且必须包含`id`字段”）。

![](img/17f4d5d915cb83e727719ecd4bbdff22_218.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_220.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_222.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_223.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_224.png)

---

![](img/17f4d5d915cb83e727719ecd4bbdff22_226.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_227.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_228.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_229.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_230.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_231.png)

## 总结

本节课我们一起学习了：
1.  **核心模型**：JSON和XML文档在内存中被表示为**树形结构**。JSON的键在边上，XML的节点名在顶点上。
2.  **关键过程**：**解析**将文本转为内存树，**序列化**将内存树转回文本。
3.  **正式定义**：以**XML信息集**为例，了解了如何正式定义数据模型的节点类型、属性和访问器。
4.  **质量层次**：区分了**良构性**（语法正确）和**验证**（结构符合模式）。
5.  **模式价值**：引入**模式**进行验证，可以规范数据结构，将异构集合变为同构集合，从而为高性能数据处理奠定基础。

![](img/17f4d5d915cb83e727719ecd4bbdff22_233.png)

理解数据如何从文本变为内存中的树，是掌握后续所有数据查询、转换和分析技术的基础。