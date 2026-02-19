# 25：数据模型 (5/5) 📊

![](img/7442510f1c3446996399d9b1ffc7cf11_0.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_2.png)

在本节课中，我们将学习XML Schema的高级特性，并深入探讨数据帧（Data Frame）的概念。我们将看到如何将JSON文档集合映射为表格形式，并理解不同数据格式（如Parquet）背后的核心思想。

![](img/7442510f1c3446996399d9b1ffc7cf11_4.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_5.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_6.png)

---

上一节我们介绍了XML Schema的基础。本节中，我们来看看XML在出版业等文本导向场景中的应用。

![](img/7442510f1c3446996399d9b1ffc7cf11_8.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_9.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_10.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_11.png)

在XML Schema中，可以使用 `mixed="true"` 来定义混合内容类型。这允许元素内部既包含文本，也包含其他子元素，类似于LaTeX中的标注方式。

```xml
<xs:complexType mixed="true">
  <xs:sequence>
    <xs:element name="B" type="xs:string" maxOccurs="unbounded"/>
  </xs:sequence>
</xs:complexType>
```

上面的Schema定义了一个复杂类型，其中可以包含字符串类型的元素 **B**，并且允许在 **B** 元素周围存在自由文本。`maxOccurs="unbounded"` 表示 **B** 元素可以出现任意多次。这是XML在处理出版物或富文本文档时的一大优势。

---

接下来，我们探讨如何验证XML属性。

![](img/7442510f1c3446996399d9b1ffc7cf11_13.png)

属性的类型与元素的原子类型相同，因为属性不能包含复杂类型。定义方式如下：

```xml
<xs:element name="person">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="lastName" type="xs:string"/>
      <xs:element name="firstName" type="xs:string"/>
    </xs:sequence>
    <xs:attribute name="birth" type="xs:date"/>
  </xs:complexType>
</xs:element>
```

![](img/7442510f1c3446996399d9b1ffc7cf11_15.png)

在这个例子中，`person` 元素是一个复杂类型，包含一个由 `lastName` 和 `firstName` 元素组成的序列，并拥有一个 `birth` 属性，其类型为 `date`。这与只包含文本的简单内容元素使用相同的类型系统。

---

![](img/7442510f1c3446996399d9b1ffc7cf11_17.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_19.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_20.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_21.png)

为了将概念具体化，我们以一个“语言游戏”的数据为例，并将其转换为XML格式。

![](img/7442510f1c3446996399d9b1ffc7cf11_23.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_24.png)

以下是转换后的XML示例结构：
```xml
<games>
  <game>
    <guess>...</guess>
    <target>...</target>
    <country>...</country>
    <choices>...</choices>
    <date>...</date>
  </game>
</games>
```

![](img/7442510f1c3446996399d9b1ffc7cf11_26.png)

在定义Schema时，需要做出设计选择：是使用元素还是属性来存储数据。例如，`sample` 在这里被定义为属性，因为它像是游戏的元数据。但请注意，这没有绝对的对错，一旦做出选择，就可以用Schema来定义和约束它。

![](img/7442510f1c3446996399d9b1ffc7cf11_28.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_29.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_30.png)

对应的Schema定义如下：
```xml
<xs:element name="games">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="game" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="guess" type="xs:string"/>
            <xs:element name="target" type="xs:string"/>
            <xs:element name="country" type="xs:string"/>
            <xs:element name="choices">
              <xs:complexType>
                <xs:sequence>
                  <xs:element name="choice" type="xs:string" maxOccurs="4"/>
                </xs:sequence>
              </xs:complexType>
            </xs:element>
            <xs:element name="date" type="xs:date"/>
          </xs:sequence>
          <xs:attribute name="sample" type="xs:hexBinary"/>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

![](img/7442510f1c3446996399d9b1ffc7cf11_32.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_33.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_34.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_36.png)

这里，`sample` 属性使用了 `hexBinary` 类型。这是一个很好的例子，用于说明词法值（lexical value）和类型值（typed value）的区别。在文档中，它可能写作 `“F8F9”` 这样的十六进制字符串，但经过Schema验证并在内存中处理后，它会被转换为一串字节。

![](img/7442510f1c3446996399d9b1ffc7cf11_38.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_39.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_41.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_43.png)

---

![](img/7442510f1c3446996399d9b1ffc7cf11_45.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_46.png)

一个有趣的事实是，XML Schema本身也有一个用于验证其他Schema的元模式（meta-schema）。这意味着Schema可以验证自身，这同样适用于JSON Schema。这虽然更多是一种理论上的完备性体现，但非常酷。

![](img/7442510f1c3446996399d9b1ffc7cf11_48.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_49.png)

---

![](img/7442510f1c3446996399d9b1ffc7cf11_51.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_52.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_53.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_54.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_55.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_57.png)

现在，让我们转向数据帧（Data Frame）的概念。如果你通过Pandas或Spark了解过数据帧，本节将从另一个角度——即有效JSON文档的集合——来阐释它。

![](img/7442510f1c3446996399d9b1ffc7cf11_59.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_60.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_61.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_62.png)

假设我们有一个JSON Schema，它定义了三个键：`id`（整数）、`name`（字符串）、`living`（布尔值），并且默认是封闭的（`"additionalProperties": false`），不允许额外属性。

![](img/7442510f1c3446996399d9b1ffc7cf11_63.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_65.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_67.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_68.png)

```json
{
  "type": "object",
  "properties": {
    "id": { "type": "integer" },
    "name": { "type": "string" },
    "living": { "type": "boolean" }
  },
  "additionalProperties": false
}
```

![](img/7442510f1c3446996399d9b1ffc7cf11_69.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_71.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_72.png)

同时，我们有以下四个符合该Schema的JSON文档：
```json
{"id": 1, "name": "Einstein", "living": false}
{"id": 2, "name": "Newton", "living": false}
{"id": 3, "name": "Turing", "living": false}
{"id": 4, "name": "Lovelace", "living": false}
```

![](img/7442510f1c3446996399d9b1ffc7cf11_73.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_75.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_76.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_78.png)

这些文档可以非常直观地表示为一个表格（数据帧）：

![](img/7442510f1c3446996399d9b1ffc7cf11_80.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_82.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_84.png)

| id | name      | living |
|----|-----------|--------|
| 1  | Einstein  | false  |
| 2  | Newton    | false  |
| 3  | Turing    | false  |
| 4  | Lovelace  | false  |

![](img/7442510f1c3446996399d9b1ffc7cf11_86.png)

**核心观点**：如果一个JSON文档序列能够根据某个Schema成功验证，那么我们就可以从表格的视角来看待这些相同的数据。数据帧本质上就是符合特定Schema的JSON对象集合。

这也是为什么在JSON Schema中，我们默认将对象设置为“封闭”的。因为在数据帧中，你不能有额外的列。如果允许额外属性，就无法将其映射到规整的数据帧结构。

---

数据帧可以处理比简单表格更复杂的嵌套结构。

**示例1：数组字段**
如果 `name` 字段是一个字符串数组，数据帧的表示会有一列包含多个值，这违反了数据库的第一范式。

![](img/7442510f1c3446996399d9b1ffc7cf11_88.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_90.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_92.png)

对应的JSON文档示例：
```json
{"id": 1, "name": ["Albert", "Einstein"], "living": false}
```

![](img/7442510f1c3446996399d9b1ffc7cf11_94.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_96.png)

**示例2：嵌套对象**
如果数据包含嵌套对象，例如 `name` 包含 `first` 和 `last` 子字段，在数据帧中会通过多级表头来表现。

![](img/7442510f1c3446996399d9b1ffc7cf11_98.png)

对应的JSON文档示例：
```json
{"id": 1, "name": {"first": "Albert", "last": "Einstein"}, "living": false}
```

![](img/7442510f1c3446996399d9b1ffc7cf11_100.png)

**示例3：对象数组**
如果有一个字段是对象数组（例如 `who`），数据帧会通过展开的方式来表示，形成一种“不完全贯穿”的表格形式。

对应的JSON文档示例：
```json
{
  "id": 1,
  "who": [
    {"name": "Albert", "type": "first"},
    {"name": "Einstein", "type": "last"}
  ],
  "living": false
}
```

![](img/7442510f1c3446996399d9b1ffc7cf11_102.png)

重要的是，存在一种约束较少的JSON结构（使用平行的 `name` 和 `type` 数组），也能映射到完全相同的数据帧视觉表现。这体现了两种表示形式之间的对偶性，在实践中可以根据需要相互转换。

---

![](img/7442510f1c3446996399d9b1ffc7cf11_104.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_106.png)

理解数据帧是有效JSON对象的集合后，我们就知道有比纯JSON更高效的存储方式。

![](img/7442510f1c3446996399d9b1ffc7cf11_108.png)

如果你从网上下载了一个符合特定Schema的巨大JSON数据集，并且可以将其转换为数据帧，那么你应该做的第一件事就是验证它，并将其转换为Parquet之类的列式存储格式。这是因为：
1.  **磁盘空间更小**：二进制格式比文本格式（如JSON）更紧凑。
2.  **读取效率更高**：列式存储便于压缩和选择性读取，优化了查询性能。
3.  **支持复杂嵌套**：像Google的Dremel论文中描述的格式，能高效地存储和读取嵌套数据。

![](img/7442510f1c3446996399d9b1ffc7cf11_110.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_111.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_112.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_113.png)

---

![](img/7442510f1c3446996399d9b1ffc7cf11_115.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_116.png)

我们可以从几个高级维度对数据进行分类：

![](img/7442510f1c3446996399d9b1ffc7cf11_118.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_119.png)

1.  **扁平 vs. 嵌套**
    *   **扁平数据**：符合第一范式，是规整的表格。
    *   **嵌套数据**：包含数组或嵌套对象，在数据帧中表现为“未完全贯穿”的列。

![](img/7442510f1c3446996399d9b1ffc7cf11_121.png)

2.  **同构 vs. 异构**
    *   **同构数据**：所有记录具有完全相同的列（属性）和类型。
    *   **异构数据**：记录间可能缺少某些属性，或包含额外的、模式中未定义的属性。传统数据帧不支持异构，但一些新系统（如Snowflake的Variant类型）开始引入支持。

![](img/7442510f1c3446996399d9b1ffc7cf11_123.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_125.png)

3.  **文本格式 vs. 二进制格式**
    *   **文本格式**：如CSV、JSON、XML、YAML。人类可读，但体积大，解析慢。
    *   **二进制格式**：如Parquet、Protocol Buffers、Avro。体积小，读写快，但不可直接阅读。

4.  **是否需要模式（Schema）**
    *   **无模式**：如灵活的NoSQL文档存储。灵活，但性能可能较低。
    *   **有模式**：如Parquet、Protocol Buffers。提供结构保证，能实现高性能和低内存占用。

![](img/7442510f1c3446996399d9b1ffc7cf11_127.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_129.png)

以下是一些常见格式及其特性：
*   **CSV**：扁平，文本，通常无严格模式。
*   **JSON Lines**：可嵌套，文本，可有可无模式。
*   **XML**：可嵌套，文本，可有可无模式。
*   **Parquet**：可嵌套，二进制，需要模式。
*   **Protocol Buffers**：可嵌套，二进制，需要模式。
*   **Avro**：可嵌套，二进制，需要模式。

![](img/7442510f1c3446996399d9b1ffc7cf11_131.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_132.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_133.png)

---

![](img/7442510f1c3446996399d9b1ffc7cf11_134.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_136.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_138.png)

好消息是，你现在已经掌握了理解所有这些格式的核心概念。当你遇到一个新格式时，只需问自己几个问题：
1.  它支持嵌套数据吗？
2.  它是文本还是二进制的？
3.  它需要预定义模式吗？
4.  它的原子类型和结构类型是什么？（你会发现它们与JSON Schema或XML Schema中的概念惊人地相似）

![](img/7442510f1c3446996399d9b1ffc7cf11_140.png)

例如，查看Parquet或Protocol Buffers的文档，你会看到熟悉的整数、字符串、布尔值等类型，只是名称可能略有不同。结构方面，它们也使用数组（或列表）和映射（或对象）的概念。

![](img/7442510f1c3446996399d9b1ffc7cf11_142.png)

---

![](img/7442510f1c3446996399d9b1ffc7cf11_144.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_146.png)

本节课中我们一起学习了：
1.  XML Schema处理混合内容和属性的方法。
2.  **数据帧的本质**：它是**符合特定约束的JSON文档集合的表格化视图**。
3.  数据可以根据**扁平/嵌套**、**同构/异构**等特性进行分类。
4.  从灵活的、无模式的JSON文档，到有模式的、高效的数据帧（如Parquet格式），是一个在性能与灵活性之间权衡的过程。
5.  大数据和NoSQL生态的魅力在于，你可以根据需求，动态地在这些表示形式之间进行转换。

![](img/7442510f1c3446996399d9b1ffc7cf11_147.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_149.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_151.png)

掌握这些核心数据模型概念，是理解和高效处理各种大数据格式与技术的基础。