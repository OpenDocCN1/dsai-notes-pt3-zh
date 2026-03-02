#  018：数据模型与验证 📚

在本节课中，我们将要学习数据模型的核心概念，特别是如何通过模式（Schema）来验证XML和JSON文档的结构。我们将理解“格式良好”与“有效”的区别，探索XML Schema的基础知识，并最终建立起数据框架（Data Frame）与已验证JSON文档集合之间的重要联系。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_1.png)

---

## 格式良好 vs. 有效

![](img/ffe5337fdb30d4edd2958be52ed6a43f_3.png)

上一节我们介绍了XML的基本结构，本节中我们来看看如何判断一个XML文档的正确性。这里有两个关键概念：**格式良好** 和 **有效**。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_5.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_6.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_7.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_8.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_9.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_10.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_11.png)

*   **格式良好**：指文档的语法是否正确。例如，所有标签是否闭合、属性值是否用引号括起来、是否只有一个根元素等。这是一个**二元判断**，无需外部信息即可确定。
*   **有效**：指文档的内容和结构是否符合某个预定义的**模式**（Schema）的规则。这需要依赖外部模式文件来判断。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_13.png)

一个文档可以是格式良好但无效的（符合语法但不符合业务规则），但一个有效的文档首先必须是格式良好的。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_14.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_15.png)

**核心公式**：
`有效(文档) = 格式良好(文档) AND 符合模式(文档, 模式)`

---

![](img/ffe5337fdb30d4edd2958be52ed6a43f_17.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_18.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_19.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_20.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_22.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_23.png)

## XML Schema 基础

为了验证XML文档的有效性，我们需要使用XML Schema语言。XML Schema本身也是一个XML文档，它使用特定的命名空间（通常是 `xs:` 或 `xsd:`）来定义规则。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_25.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_27.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_28.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_30.png)

### 声明简单元素

一个简单元素只包含文本内容，没有子元素或属性。以下是声明一个名为 `who` 的字符串类型元素的模式：

![](img/ffe5337fdb30d4edd2958be52ed6a43f_32.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_33.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_34.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_35.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_36.png)

```xml
<xs:element name="who" type="xs:string"/>
```
对应的有效XML实例如下：
```xml
<who>Albert Einstein</who>
```

### 声明复杂元素与序列

![](img/ffe5337fdb30d4edd2958be52ed6a43f_38.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_39.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_40.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_42.png)

复杂元素可以包含子元素和/或属性。使用 `<xs:complexType>` 和 `<xs:sequence>` 可以定义子元素必须出现的顺序。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_44.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_45.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_46.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_47.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_48.png)

以下模式定义了一个 `person` 元素，它必须按顺序包含 `last` 和 `first` 两个子元素：
```xml
<xs:element name="person">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="last" type="xs:string"/>
      <xs:element name="first" type="xs:string"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```
对应的有效XML实例如下：
```xml
<person>
  <last>Einstein</last>
  <first>Albert</first>
</person>
```

![](img/ffe5337fdb30d4edd2958be52ed6a43f_50.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_51.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_52.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_53.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_54.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_56.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_58.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_59.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_60.png)

### 控制元素出现次数

![](img/ffe5337fdb30d4edd2958be52ed6a43f_62.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_64.png)

使用 `minOccurs` 和 `maxOccurs` 属性可以控制子元素出现的次数。默认值均为1。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_66.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_67.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_68.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_69.png)

以下模式允许 `item` 元素出现2到4次：
```xml
<xs:element name="item" type="xs:string" minOccurs="2" maxOccurs="4"/>
```
`maxOccurs=”unbounded”` 表示出现次数无上限。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_71.png)

### 处理混合内容

![](img/ffe5337fdb30d4edd2958be52ed6a43f_73.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_74.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_75.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_76.png)

混合内容允许元素内部同时包含文本和子元素，这在出版业（如标记文档中的段落和格式）中很常见。通过设置 `mixed=”true”` 来实现。

以下模式允许 `p` 元素内混合文本和 `b`、`i` 子元素：
```xml
<xs:element name="p">
  <xs:complexType mixed="true">
    <xs:sequence>
      <xs:element name="b" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="i" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```
对应的有效XML实例如下：
```xml
<p>这是一段 <b>加粗</b> 和 <i>斜体</i> 混合的文本。</p>
```

![](img/ffe5337fdb30d4edd2958be52ed6a43f_78.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_80.png)

### 声明与验证属性

属性在 `<xs:complexType>` 内部，紧接在子元素序列之后使用 `<xs:attribute>` 声明。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_82.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_83.png)

以下模式为 `person` 元素添加了一个 `birth` 属性，其类型为日期：
```xml
<xs:element name="person">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="last" type="xs:string"/>
      <xs:element name="first" type="xs:string"/>
    </xs:sequence>
    <xs:attribute name="birth" type="xs:date"/>
  </xs:complexType>
</xs:element>
```
对应的有效XML实例如下：
```xml
<person birth="1879-03-14">
  <last>Einstein</last>
  <first>Albert</first>
</person>
```

---

## 从已验证文档到数据框架

![](img/ffe5337fdb30d4edd2958be52ed6a43f_85.png)

理解了如何用模式验证单个文档后，我们来看一个更强大的概念。一个**数据框架**本质上可以看作是一个**符合相同模式的JSON文档集合**的可视化表格形式。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_87.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_89.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_90.png)

### 数据框架是有效的文档集合

![](img/ffe5337fdb30d4edd2958be52ed6a43f_92.png)

假设我们有一个简单的JSON Schema，它定义了包含 `id`（整数）、`name`（字符串）和 `living`（布尔值）的对象。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_94.png)

一个符合该模式的数据框架可视化如下：

![](img/ffe5337fdb30d4edd2958be52ed6a43f_96.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_97.png)

| id | name      | living |
|----|-----------|--------|
| 1  | Einstein  | false  |
| 2  | Meitner   | false  |
| 3  | Turing    | false  |
| 4  | Lovelace  | false  |

这个表格中的每一行，都对应一个有效的JSON对象：
```json
{"id": 1, "name": "Einstein", "living": false}
```

![](img/ffe5337fdb30d4edd2958be52ed6a43f_99.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_101.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_103.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_105.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_107.png)

### 数据框架支持嵌套结构

![](img/ffe5337fdb30d4edd2958be52ed6a43f_108.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_110.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_111.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_112.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_114.png)

数据框架比传统的关系型数据库表更强大，因为它可以优雅地表示嵌套结构，这正是JSON等格式所擅长的。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_115.png)

1.  **嵌套数组**：如果 `name` 在模式中被定义为字符串数组，数据框架可以这样表示：
    | id | name          | living |
    |----|---------------|--------|
    | 1  | [“Albert”, “Einstein”] | false  |
    | 2  | [“Lise”]      | false  |

![](img/ffe5337fdb30d4edd2958be52ed6a43f_117.png)

2.  **嵌套对象**：如果 `name` 是一个包含 `first` 和 `last` 键的对象，数据框架会通过分层表头来展示：
    | id | name.first | name.last | living |
    |----|------------|-----------|--------|
    | 1  | Albert     | Einstein  | false  |

![](img/ffe5337fdb30d4edd2958be52ed6a43f_119.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_121.png)

3.  **对象数组（嵌套表）**：如果 `who` 是一个对象数组，每个对象有 `name` 和 `type` 字段，数据框架会将其显示为嵌套表：
    | id | who.name | who.type | living |
    |----|----------|----------|--------|
    | 1  | Albert   | first    | false  |
    | 1  | Einstein | last     | false  |
    | 2  | Lise     | first    | false  |

**关键约束**：为了能稳定地映射到数据框架，背后的JSON Schema通常需要满足一些条件，例如不允许过于泛化的类型（如 `item`），并且通常要求是“封闭对象”（不允许未在模式中定义的额外键）。

---

## 数据格式的分类

最后，让我们从更高视角对不同的数据存储格式进行分类。任何数据集，无论是XML、JSON还是其他格式，都可以抽象为 **“映射的列表”**（List of Maps），即一系列记录（行），每条记录是一个键值对集合（列）。

我们可以从三个维度对数据格式进行分类：

以下是主要的分类维度：

1.  **结构：扁平 vs. 嵌套**
    *   **扁平格式**：如CSV，每个“单元格”都是原子值（字符串、数字等），不支持嵌套结构。
    *   **嵌套格式**：如JSON、XML、YAML、Parquet、Protocol Buffers，允许值本身是数组或对象，形成树状结构。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_123.png)

2.  **编码：文本 vs. 二进制**
    *   **文本格式**：如JSON、XML、CSV、YAML。人类可读，可以用文本编辑器打开，但通常体积较大。
    *   **二进制格式**：如Parquet、Avro、Protocol Buffers。机器优化，体积小，读写速度快，节省存储空间和I/O带宽，但不可直接阅读。

3.  **模式：是否需要模式**
    *   **模式可选**：如JSON、XML、YAML。没有模式也能使用，灵活性高，常用于数据交换。
    *   **模式必需**：如Parquet、Avro、Protocol Buffers。必须预定义模式才能读写，这种约束带来了高效压缩、强类型检查和更好的性能，常用于数据存储和处理。

**重要实践**：从网络获取的文本格式（如JSON）数据集，如果需要在系统中反复查询分析，将其转换为二进制格式（如Parquet）通常是提高性能的最佳实践。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_125.png)

---

![](img/ffe5337fdb30d4edd2958be52ed6a43f_127.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_128.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_129.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_130.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_131.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_132.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_133.png)

## 总结

![](img/ffe5337fdb30d4edd2958be52ed6a43f_135.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_136.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_138.png)

本节课中我们一起学习了数据模型验证的核心思想。我们明确了文档“格式良好”与“有效”的根本区别，并深入了解了如何使用XML Schema来定义和验证XML文档的结构。更重要的是，我们建立了数据框架与已验证JSON文档集合之间的深刻联系，认识到数据框架实质上是具有一致结构的半结构化数据的表格化视图。最后，我们从结构、编码和模式需求三个维度对常见数据格式进行了分类，理解了不同格式的适用场景，特别是二进制格式对于大数据处理的重要性。这些概念为我们后续学习数据框架操作和MapReduce等分布式处理框架奠定了坚实的基础。