# 课程9：《开发数据产品》｜P44：创建你的第一个Swirl课程 📘

![](img/6a2e6952a1275290dcddde84e55a3a07_0.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_2.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_4.png)

在本节课中，我们将学习如何使用 `swirlify` 包来创建和编写你自己的交互式Swirl课程。我们将从创建一个新课程和新课节开始，逐步添加不同类型的问题，并最终测试和运行这个课程。

![](img/6a2e6952a1275290dcddde84e55a3a07_6.png)

---

![](img/6a2e6952a1275290dcddde84e55a3a07_8.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_9.png)

## 1. 准备工作与创建课程 🛠️

![](img/6a2e6952a1275290dcddde84e55a3a07_11.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_13.png)

首先，你需要加载 `swirlify` 包。这个包是创建和管理Swirl课程的核心工具。

![](img/6a2e6952a1275290dcddde84e55a3a07_15.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_17.png)

```r
library(swirlify)
```

`swirlify` 始终知晓你的当前工作目录。为了组织方便，建议为你的Swirl课程创建一个专用目录。例如，你可以在桌面上创建一个名为 `courses` 的文件夹。

![](img/6a2e6952a1275290dcddde84e55a3a07_19.png)

```r
setwd("~/Desktop/courses")
```

![](img/6a2e6952a1275290dcddde84e55a3a07_20.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_21.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_22.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_23.png)

准备工作完成后，我们可以开始创建新的课程和课节了。

![](img/6a2e6952a1275290dcddde84e55a3a07_25.png)

---

![](img/6a2e6952a1275290dcddde84e55a3a07_27.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_29.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_31.png)

## 2. 创建新课节与课程结构 📁

![](img/6a2e6952a1275290dcddde84e55a3a07_33.png)

你可以使用 `new_lesson` 函数来同时创建一个新课程和一个新课节。

![](img/6a2e6952a1275290dcddde84e55a3a07_35.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_36.png)

```r
new_lesson(lesson_name = "Lesson One", course_name = "My First Course")
```

![](img/6a2e6952a1275290dcddde84e55a3a07_38.png)

执行这个函数会完成几件事：
1.  它会打开一个YAML文件。所有Swirl课节都是用YAML（一种易于理解的标记语言）编写的。
2.  它会创建课程和课节的文件夹结构。

![](img/6a2e6952a1275290dcddde84e55a3a07_40.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_42.png)

让我们来看看创建的文件结构。在 `courses` 目录下，现在会有一个名为 `My_First_Course` 的文件夹，里面包含一个名为 `Lesson_One` 的子文件夹。

![](img/6a2e6952a1275290dcddde84e55a3a07_44.png)

以下是 `Lesson_One` 文件夹内生成的关键文件：

![](img/6a2e6952a1275290dcddde84e55a3a07_46.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_47.png)

*   **`customTests.R`**：你可以在这里指定用于测试问题答案正确性的自定义函数。我们稍后会讨论答案测试。
*   **`dependson.txt`**：这是一个文本文件，用于列出本课节依赖的R包。Swirl会在课节开始前检查这些包是否已安装。
*   **`initLesson.R`**：这是一个R脚本。你在这里编写的任何代码都会在课节开始前执行。例如，你可以在这里加载数据，或者创建学生将在课节中用到的函数。
*   **`lesson.yaml`**：这就是我们刚才看到的YAML文件，它是课节内容的核心，所有问题和指令都写在这里。

推荐使用RStudio来编写Swirl课节，因为将文本编辑器和R控制台并排显示在同一屏幕上非常方便。当然，你也可以选择适合自己的工作流程。

![](img/6a2e6952a1275290dcddde84e55a3a07_49.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_50.png)

---

![](img/6a2e6952a1275290dcddde84e55a3a07_51.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_52.png)

## 3. 编写课节内容：添加问题 ✍️

![](img/6a2e6952a1275290dcddde84e55a3a07_54.png)

现在我们已经设置好了新课节，可以开始添加问题了。`swirlify` 提供了一系列以 `wq_` 开头的函数，用于添加不同类型的问题。

![](img/6a2e6952a1275290dcddde84e55a3a07_55.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_56.png)

### 添加消息类问题

最简单的题型是“消息”类问题，它只向学生显示信息，不要求输入。使用 `wq_message()` 函数。

```r
wq_message()
```

![](img/6a2e6952a1275290dcddde84e55a3a07_58.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_59.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_60.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_61.png)

执行后，`lesson.yaml` 文件中会添加一个消息问题的模板。你可以编辑它，例如：

![](img/6a2e6952a1275290dcddde84e55a3a07_62.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_63.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_65.png)

```yaml
- Class: text
  Output: Welcome to Lesson One.
```

### 添加命令类问题

![](img/6a2e6952a1275290dcddde84e55a3a07_67.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_68.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_69.png)

接下来，让我们添加一个“命令”类问题，它会提示学生在R控制台中输入代码。使用 `wq_command()` 函数。

![](img/6a2e6952a1275290dcddde84e55a3a07_71.png)

```r
wq_command()
```

![](img/6a2e6952a1275290dcddde84e55a3a07_73.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_74.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_76.png)

同样，模板会被添加到 `lesson.yaml` 文件中。现在我们来编辑它，创建一个简单的问题：

![](img/6a2e6952a1275290dcddde84e55a3a07_78.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_80.png)

*   **问题**：`Add 2 and 2 using the plus operator.`
*   **正确答案**：`2 + 2`
*   **答案测试**：`omnitest`。这是一个Swirl自带的函数，用于测试学生输入的答案。80%到90%的情况下你都可以使用它。
*   **提示**：`Type 2 + 2`

编辑后的YAML部分如下所示：

![](img/6a2e6952a1275290dcddde84e55a3a07_82.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_83.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_84.png)

```yaml
- Class: cmd_question
  Output: Add 2 and 2 using the plus operator.
  CorrectAnswer: 2 + 2
  AnswerTests: omnitest(correctExpr='2 + 2')
  Hint: Type 2 + 2.
```

![](img/6a2e6952a1275290dcddde84e55a3a07_86.png)

---

![](img/6a2e6952a1275290dcddde84e55a3a07_87.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_89.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_91.png)

## 4. 管理课程清单与测试课节 ✅

![](img/6a2e6952a1275290dcddde84e55a3a07_93.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_95.png)

编写完问题后，需要将课节添加到课程的清单中。这可以通过 `add_to_manifest()` 函数轻松完成。

```r
add_to_manifest()
```

![](img/6a2e6952a1275290dcddde84e55a3a07_97.png)

这个操作会在课程目录（`My_First_Course`）下创建一个 `MANIFEST` 文件。这个文件有两个作用：
1.  记录课程中包含哪些课节。
2.  定义课节显示的顺序。
这样，如果你在课程文件夹中存放了数据或其他文件，它们不会作为可选的课节出现在学生的菜单里，有助于保持项目结构清晰。

![](img/6a2e6952a1275290dcddde84e55a3a07_98.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_99.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_100.png)

现在，是时候测试我们的课节了。

首先，使用 `test_lesson()` 函数来检查课节的格式是否正确。

![](img/6a2e6952a1275290dcddde84e55a3a07_102.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_103.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_104.png)

```r
test_lesson()
```

如果没有收到任何警告或错误信息，说明课节通过了基本的格式检查。

![](img/6a2e6952a1275290dcddde84e55a3a07_106.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_107.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_108.png)

接着，使用 `demo_lesson()` 函数来实际运行这个课节，进行体验。

![](img/6a2e6952a1275290dcddde84e55a3a07_110.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_111.png)

```r
demo_lesson()
```

![](img/6a2e6952a1275290dcddde84e55a3a07_112.png)

这个函数会直接启动你正在编写的课节，无需经过Swirl的常规菜单。你会看到第一个消息：“Welcome to Lesson One.”。然后，会出现命令问题：“Add 2 and 2 using the plus operator.”。输入 `2 + 2` 后，课节便顺利结束。

![](img/6a2e6952a1275290dcddde84e55a3a07_114.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_115.png)

---

![](img/6a2e6952a1275290dcddde84e55a3a07_117.png)

## 总结 📝

![](img/6a2e6952a1275290dcddde84e55a3a07_119.png)

本节课中，我们一起学习了创建自定义Swirl课程的基本流程：
1.  使用 `new_lesson()` 初始化课程和课节结构。
2.  了解课节文件夹中的关键文件及其作用。
3.  使用 `wq_message()` 和 `wq_command()` 等函数向 `lesson.yaml` 文件中添加不同类型的问题。
4.  使用 `add_to_manifest()` 管理课程清单。
5.  使用 `test_lesson()` 和 `demo_lesson()` 来测试和运行你的课节。

![](img/6a2e6952a1275290dcddde84e55a3a07_120.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_121.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_123.png)

你已经掌握了创建交互式R编程教程的基础。接下来，可以尝试添加更多复杂的问题类型（如多选题、图形题等），并利用 `customTests.R` 和 `initLesson.R` 文件来增强课节的功能。