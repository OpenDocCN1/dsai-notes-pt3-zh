# 045：创建更复杂的Swirl课程问题类型 🧩

![](img/6a28dee4c96abeece04a0d8d8f526db8_0.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_2.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_4.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_6.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_8.png)

在本节课中，我们将学习如何在Swirl课程中创建更复杂的问题类型，包括多选题和图形题。我们将从创建新课程开始，逐步探索这些高级功能。

![](img/6a28dee4c96abeece04a0d8d8f526db8_10.png)

上一节我们创建并测试了第一个简单的Swirl课程。本节中，我们来看看如何创建包含多选题和图形题等更复杂交互的课程。

![](img/6a28dee4c96abeece04a0d8d8f526db8_11.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_12.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_13.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_15.png)

## 创建新课程

![](img/6a28dee4c96abeece04a0d8d8f526db8_17.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_19.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_21.png)

首先，我们需要创建一个新的课程。使用 `get_current_lesson()` 函数可以查看当前正在工作的课程信息。

![](img/6a28dee4c96abeece04a0d8d8f526db8_23.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_24.png)

```r
get_current_lesson()
```

![](img/6a28dee4c96abeece04a0d8d8f526db8_25.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_26.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_28.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_30.png)

结果显示当前课程名为“my first course”。接下来，我们在这个课程下创建一个名为“lesson 2”的新课程。

![](img/6a28dee4c96abeece04a0d8d8f526db8_32.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_34.png)

## 元问题

![](img/6a28dee4c96abeece04a0d8d8f526db8_36.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_38.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_40.png)

每个Swirl课程的第一个问题被称为“元问题”。学生看不到这个问题，但开发者可以在这里填写课程的作者和组织等信息。

![](img/6a28dee4c96abeece04a0d8d8f526db8_42.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_44.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_46.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_47.png)

## 创建多选题

![](img/6a28dee4c96abeece04a0d8d8f526db8_49.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_51.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_53.png)

现在，让我们创建一个多选题。在R控制台中使用 `wq_multiple()` 函数可以添加一个多选题模板。

![](img/6a28dee4c96abeece04a0d8d8f526db8_55.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_56.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_58.png)

以下是创建多选题的步骤：

![](img/6a28dee4c96abeece04a0d8d8f526db8_60.png)

1.  在编辑器中，输入问题文本，例如：“Which of these shapes has four sides?”
2.  用分号分隔不同的选项。
3.  指定正确答案。
4.  在“答案测试”字段中重复正确答案。
5.  可以提供一个提示。

![](img/6a28dee4c96abeece04a0d8d8f526db8_62.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_63.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_64.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_66.png)

例如，一个完整的多选题配置如下：
*   **问题**：`Which of these shapes has four sides?`
*   **选项**：`circle; square; triangle`
*   **正确答案**：`square`
*   **答案测试**：`omnitest(correctVal='square')`
*   **提示**：`Think about the number of sides each shape has.`

![](img/6a28dee4c96abeece04a0d8d8f526db8_68.png)

添加课程到清单并运行 `test_lesson()` 确保没有错误后，可以使用 `demo_lesson()` 进行测试。

![](img/6a28dee4c96abeece04a0d8d8f526db8_70.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_71.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_72.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_73.png)

## 创建图形题

![](img/6a28dee4c96abeece04a0d8d8f526db8_74.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_76.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_77.png)

Swirl允许创建展示图形的题目。使用 `wq_figure()` 函数可以添加一个图形题模板。

![](img/6a28dee4c96abeece04a0d8d8f526db8_79.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_81.png)

图形题包含几个关键部分：
*   **消息**：展示给用户的文本。
*   **图形文件**：一个R脚本，其中包含生成图形的代码。
*   **图形类型**：指定是创建新图形（`new`）还是在现有图形上添加（`add`）。

![](img/6a28dee4c96abeece04a0d8d8f526db8_83.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_84.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_86.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_88.png)

### 创建新图形

![](img/6a28dee4c96abeece04a0d8d8f526db8_90.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_92.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_94.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_96.png)

首先，我们创建一个展示简单图形的新问题。
1.  将消息设置为“This is a simple graph.”
2.  创建一个名为 `fig1.R` 的R脚本文件，并保存在课程目录下。脚本内容可以是简单的绘图代码，例如 `plot(1:10)`。
3.  将图形类型设置为 `new`。

![](img/6a28dee4c96abeece04a0d8d8f526db8_98.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_100.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_102.png)

### 在图形上添加元素

![](img/6a28dee4c96abeece04a0d8d8f526db8_104.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_105.png)

接下来，我们可以创建第二个图形题，在已绘制的图形上添加新元素。
1.  再次使用 `wq_figure()` 添加一个新模板。
2.  将消息设置为“I added a line.”
3.  创建第二个R脚本文件 `fig2.R`，包含添加元素的代码，例如 `abline(h = 5)`。
4.  关键步骤：将图形类型设置为 `add`，这表示代码将在上一个图形的基础上执行。

![](img/6a28dee4c96abeece04a0d8d8f526db8_107.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_109.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_111.png)

运行 `demo_lesson()` 进行测试，学生将依次看到多选题、第一个图形，以及添加了线条的第二个图形。

![](img/6a28dee4c96abeece04a0d8d8f526db8_112.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_114.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_116.png)

---

![](img/6a28dee4c96abeece04a0d8d8f526db8_118.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_119.png)

![](img/6a28dee4c96abeece04a0d8d8f526db8_121.png)

本节课中我们一起学习了如何在Swirl中创建包含多选题和图形题的更复杂课程。我们了解了元问题的用途，掌握了使用 `wq_multiple()` 创建选择题，以及使用 `wq_figure()` 配合 `new` 和 `add` 类型来创建交互式图形演示的方法。这些工具能帮助你构建更丰富、更具互动性的数据科学教学材料。