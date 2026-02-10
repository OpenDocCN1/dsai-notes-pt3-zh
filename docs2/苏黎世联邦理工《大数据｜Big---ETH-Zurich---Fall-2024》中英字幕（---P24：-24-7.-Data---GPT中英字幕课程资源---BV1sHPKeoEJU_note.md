# 大数据课程 - ETH Zurich - Fall 2024 📚
## 第24讲：数据模型（4/5）🌳

![](img/11e074b29f767f27e7865a5da5e77a92_1.png)

![](img/11e074b29f767f27e7865a5da5e77a92_2.png)

![](img/11e074b29f767f27e7865a5da5e77a92_3.png)

![](img/11e074b29f767f27e7865a5da5e77a92_4.png)

![](img/11e074b29f767f27e7865a5da5e77a92_5.png)

在本节课中，我们将完成对数据模型的讨论。我们将重点学习如何为树形结构数据（如XML和JSON）定义和使用模式（Schema），理解模式验证的核心概念与功能，并比较几种主流模式语言（如JSON Schema和XML Schema）的异同。

![](img/11e074b29f767f27e7865a5da5e77a92_7.png)

![](img/11e074b29f767f27e7865a5da5e77a92_9.png)

![](img/11e074b29f767f27e7865a5da5e77a92_10.png)

![](img/11e074b29f767f27e7865a5da5e77a92_12.png)

---

![](img/11e074b29f767f27e7865a5da5e77a92_13.png)

![](img/11e074b29f767f27e7865a5da5e77a92_14.png)

![](img/11e074b29f767f27e7865a5da5e77a92_15.png)

![](img/11e074b29f767f27e7865a5da5e77a92_16.png)

![](img/11e074b29f767f27e7865a5da5e77a92_17.png)

![](img/11e074b29f767f27e7865a5da5e77a92_18.png)

![](img/11e074b29f767f27e7865a5da5e77a92_20.png)

![](img/11e074b29f767f27e7865a5da5e77a92_21.png)

![](img/11e074b29f767f27e7865a5da5e77a92_22.png)

上一节我们介绍了XML和JSON本质上是树形结构。本节中，我们来看看如何为这些树形数据定义结构规则，即模式验证。

![](img/11e074b29f767f27e7865a5da5e77a92_23.png)

![](img/11e074b29f767f27e7865a5da5e77a92_24.png)

![](img/11e074b29f767f27e7865a5da5e77a92_25.png)

![](img/11e074b29f767f27e7865a5da5e77a92_27.png)

![](img/11e074b29f767f27e7865a5da5e77a92_28.png)

![](img/11e074b29f767f27e7865a5da5e77a92_29.png)

![](img/11e074b29f767f27e7865a5da5e77a92_30.png)

![](img/11e074b29f767f27e7865a5da5e77a92_31.png)

模式验证允许我们在确认一个文档格式良好（well-formed）并解析为内存中的树形表示后，进一步检查它是否符合模式所规定的结构。模式定义了数据的预期形状和类型。

![](img/11e074b29f767f27e7865a5da5e77a92_33.png)

以下是模式语言通常具备的核心功能：

![](img/11e074b29f767f27e7865a5da5e77a92_35.png)

![](img/11e074b29f767f27e7865a5da5e77a92_36.png)

![](img/11e074b29f767f27e7865a5da5e77a92_37.png)

![](img/11e074b29f767f27e7865a5da5e77a92_38.png)

![](img/11e074b29f767f27e7865a5da5e77a92_40.png)

![](img/11e074b29f767f27e7865a5da5e77a92_41.png)

![](img/11e074b29f767f27e7865a5da5e77a92_42.png)

![](img/11e074b29f767f27e7865a5da5e77a92_43.png)

1.  **类型限制**：可以指定某个键（key）对应的值必须是特定类型。
    *   **公式/代码示例**：`"last": string` 或 `"age": integer`

2.  **隐式类型转换（注解）**：验证过程不仅检查值，还可能将其从文本形式（词法值）转换为内存中的特定类型。
    *   **公式/代码示例**：词法值 `"42"` (字符串) 在通过 `integer` 类型验证后，在内存中被转换为整数 `42`。

![](img/11e074b29f767f27e7865a5da5e77a92_45.png)

![](img/11e074b29f767f27e7865a5da5e77a92_47.png)

![](img/11e074b29f767f27e7865a5da5e77a92_48.png)

3.  **字段必选/可选**：可以指定某个键是必须存在的（必选）还是可以省略的（可选）。默认设置是可选还是必选，是模式语言的设计选择。

4.  **控制额外字段**：可以指定是否允许实例中出现模式中未定义的额外字段。同样，默认允许或禁止也是设计决策。

![](img/11e074b29f767f27e7865a5da5e77a92_50.png)

![](img/11e074b29f767f27e7865a5da5e77a92_51.png)

![](img/11e074b29f767f27e7865a5da5e77a92_52.png)

5.  **默认值**：可以指定当实例中缺少某个可选键时，系统应自动填充的默认值。

![](img/11e074b29f767f27e7865a5da5e77a92_54.png)

![](img/11e074b29f767f27e7865a5da5e77a92_56.png)

6.  **主键定义**：对于对象数组（类似于表格），可以指定哪个或哪些字段构成主键，并确保其唯一性。

---

![](img/11e074b29f767f27e7865a5da5e77a92_58.png)

![](img/11e074b29f767f27e7865a5da5e77a92_60.png)

![](img/11e074b29f767f27e7865a5da5e77a92_62.png)

![](img/11e074b29f767f27e7865a5da5e77a92_63.png)

### 模式语言设计：静态与动态语法

设计模式语言时，语法可以是静态的或动态的。

![](img/11e074b29f767f27e7865a5da5e77a92_65.png)

![](img/11e074b29f767f27e7865a5da5e77a92_66.png)

![](img/11e074b29f767f27e7865a5da5e77a92_67.png)

![](img/11e074b29f767f27e7865a5da5e77a92_68.png)

![](img/11e074b29f767f27e7865a5da5e77a92_69.png)

*   **静态语法**：模式中的键（属性名）是预定义、固定的。用户只能改变这些键对应的值。这使得语法可预测且易于工具处理。
*   **动态语法**：模式中的键可以由模式设计者自由定义，更接近实例本身的结构，可能更直观，但灵活性可能导致设计复杂。

![](img/11e074b29f767f27e7865a5da5e77a92_71.png)

![](img/11e074b29f767f27e7865a5da5e77a92_72.png)

![](img/11e074b29f767f27e7865a5da5e77a92_73.png)

![](img/11e074b29f767f27e7865a5da5e77a92_74.png)

![](img/11e074b29f767f27e7865a5da5e77a92_75.png)

![](img/11e074b29f767f27e7865a5da5e77a92_77.png)

![](img/11e074b29f767f27e7865a5da5e77a92_78.png)

![](img/11e074b29f767f27e7865a5da5e77a92_79.png)

![](img/11e074b29f767f27e7865a5da5e77a92_80.png)

![](img/11e074b29f767f27e7865a5da5e77a92_81.png)

许多模式语言（如JSON Schema）混合使用了这两种方式。

![](img/11e074b29f767f27e7865a5da5e77a92_83.png)

![](img/11e074b29f767f27e7865a5da5e77a92_84.png)

![](img/11e074b29f767f27e7865a5da5e77a92_85.png)

![](img/11e074b29f767f27e7865a5da5e77a92_86.png)

![](img/11e074b29f767f27e7865a5da5e77a92_87.png)

![](img/11e074b29f767f27e7865a5da5e77a92_89.png)

![](img/11e074b29f767f27e7865a5da5e77a92_90.png)

![](img/11e074b29f767f27e7865a5da5e77a92_91.png)

![](img/11e074b29f767f27e7865a5da5e77a92_92.png)

---

![](img/11e074b29f767f27e7865a5da5e77a92_94.png)

![](img/11e074b29f767f27e7865a5da5e77a92_95.png)

![](img/11e074b29f767f27e7865a5da5e77a92_97.png)

![](img/11e074b29f767f27e7865a5da5e77a92_98.png)

![](img/11e074b29f767f27e7865a5da5e77a92_99.png)

### JSON Schema 示例

![](img/11e074b29f767f27e7865a5da5e77a92_101.png)

![](img/11e074b29f767f27e7865a5da5e77a92_102.png)

![](img/11e074b29f767f27e7865a5da5e77a92_104.png)

![](img/11e074b29f767f27e7865a5da5e77a92_105.png)

![](img/11e074b29f767f27e7865a5da5e77a92_106.png)

JSON Schema 是一个广泛使用的模式语言。其模式本身也是一个JSON文档。

![](img/11e074b29f767f27e7865a5da5e77a92_108.png)

![](img/11e074b29f767f27e7865a5da5e77a92_109.png)

![](img/11e074b29f767f27e7865a5da5e77a92_111.png)

![](img/11e074b29f767f27e7865a5da5e77a92_112.png)

![](img/11e074b29f767f27e7865a5da5e77a92_114.png)

![](img/11e074b29f767f27e7865a5da5e77a92_115.png)

以下是一个简单的JSON Schema示例，它要求一个对象必须有 `"last"` 字段（字符串类型），并可选地包含 `"first"` 字段（字符串类型）：

![](img/11e074b29f767f27e7865a5da5e77a92_117.png)

![](img/11e074b29f767f27e7865a5da5e77a92_118.png)

![](img/11e074b29f767f27e7865a5da5e77a92_119.png)

![](img/11e074b29f767f27e7865a5da5e77a92_121.png)

![](img/11e074b29f767f27e7865a5da5e77a92_122.png)

![](img/11e074b29f767f27e7865a5da5e77a92_124.png)

```json
{
  "type": "object",
  "properties": {
    "last": { "type": "string" },
    "first": { "type": "string" }
  },
  "required": ["last"],
  "additionalProperties": false
}
```

![](img/11e074b29f767f27e7865a5da5e77a92_126.png)

![](img/11e074b29f767f27e7865a5da5e77a92_128.png)

*   `"type"`, `"properties"`, `"required"`, `"additionalProperties"` 是静态的关键字。
*   `"last"` 和 `"first"` 是动态定义的属性名。
*   `"required": ["last"]` 使 `last` 字段成为必选。
*   `"additionalProperties": false` 禁止出现任何未在 `properties` 中定义的额外字段。

![](img/11e074b29f767f27e7865a5da5e77a92_130.png)

![](img/11e074b29f767f27e7865a5da5e77a92_131.png)

![](img/11e074b29f767f27e7865a5da5e77a92_132.png)

---

### XML Schema 示例

XML Schema 用于定义XML文档的结构，其模式本身也是XML格式，并且完全采用静态语法。

以下是一个简单的XML Schema示例，它定义了一个 `person` 元素，其中必须按顺序包含 `last` 和 `first` 子元素，且两者都是字符串类型：

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="person">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="last" type="xs:string"/>
        <xs:element name="first" type="xs:string" minOccurs="0"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

*   `schema`, `element`, `complexType`, `sequence`, `minOccurs` 都是预定义的静态元素和属性。
*   `minOccurs="0"` 使 `first` 元素成为可选的。

---

### 类型系统与映射

理解数据模型时，一个重要概念是**类型系统映射**或**阻抗不匹配**。

![](img/11e074b29f767f27e7865a5da5e77a92_134.png)

![](img/11e074b29f767f27e7865a5da5e77a92_135.png)

![](img/11e074b29f767f27e7865a5da5e77a92_137.png)

*   **词法空间 vs. 值空间**：原始数据（如JSON中的 `"42"`）是词法值。模式验证检查该词法值是否属于目标类型（如 `integer`）的词法空间。通过后，它被转换为该类型的值（整数 `42`）。
*   **跨语言差异**：不同的编程语言（Python, Java, JavaScript）和数据处理框架（Spark, Pandas）拥有不同的类型系统。将一种模式语言（如JSON Schema）定义的类型映射到具体执行环境的类型时，需要仔细定义映射关系。例如，一个没有小数点的数字可能被映射为Python的 `int` 或Java的 `Long`，这取决于具体实现。

![](img/11e074b29f767f27e7865a5da5e77a92_139.png)

![](img/11e074b29f767f27e7865a5da5e77a92_140.png)

![](img/11e074b29f767f27e7865a5da5e77a92_141.png)

![](img/11e074b29f767f27e7865a5da5e77a92_142.png)

---

![](img/11e074b29f767f27e7865a5da5e77a92_144.png)

![](img/11e074b29f767f27e7865a5da5e77a92_146.png)

### 总结

![](img/11e074b29f767f27e7865a5da5e77a92_148.png)

![](img/11e074b29f767f27e7865a5da5e77a92_149.png)

![](img/11e074b29f767f27e7865a5da5e77a92_150.png)

![](img/11e074b29f767f27e7865a5da5e77a92_151.png)

![](img/11e074b29f767f27e7865a5da5e77a92_152.png)

![](img/11e074b29f767f27e7865a5da5e77a92_153.png)

![](img/11e074b29f767f27e7865a5da5e77a92_154.png)

![](img/11e074b29f767f27e7865a5da5e77a92_155.png)

![](img/11e074b29f767f27e7865a5da5e77a92_156.png)

![](img/11e074b29f767f27e7865a5da5e77a92_157.png)

本节课中我们一起学习了数据模型的核心环节——模式验证。

![](img/11e074b29f767f27e7865a5da5e77a92_159.png)

![](img/11e074b29f767f27e7865a5da5e77a92_161.png)

![](img/11e074b29f767f27e7865a5da5e77a92_162.png)

![](img/11e074b29f767f27e7865a5da5e77a92_163.png)

![](img/11e074b29f767f27e7865a5da5e77a92_164.png)

我们了解到，模式验证为树形数据（JSON/XML）提供了结构、类型和约束的定义能力。无论是JSON Schema、XML Schema还是其他模式语言，它们都共享诸如类型约束、必选/可选字段、控制额外字段、默认值等核心功能。这些语言在语法设计上可能有静态和动态之分，但其目标一致：确保数据符合预期结构。

![](img/11e074b29f767f27e7865a5da5e77a92_166.png)

![](img/11e074b29f767f27e7865a5da5e77a92_167.png)

![](img/11e074b29f767f27e7865a5da5e77a92_168.png)

![](img/11e074b29f767f27e7865a5da5e77a92_170.png)

![](img/11e074b29f767f27e7865a5da5e77a92_172.png)

![](img/11e074b29f767f27e7865a5da5e77a92_173.png)

理解模式语言的关键在于把握其设计理念，而不仅仅是记忆特定语法。这包括如何处理默认行为、类型转换以及在不同系统间的类型映射。掌握这些概念，将有助于你在未来轻松学习和应用各种数据定义与验证工具。

![](img/11e074b29f767f27e7865a5da5e77a92_175.png)

![](img/11e074b29f767f27e7865a5da5e77a92_177.png)

![](img/11e074b29f767f27e7865a5da5e77a92_178.png)

---