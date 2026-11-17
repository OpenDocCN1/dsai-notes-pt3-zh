# 044：创建你的第一个Swirl课程 📘




在本节课中，我们将学习如何使用 `swirlify` 包来创建和编写你自己的交互式Swirl课程。我们将从创建一个新课程和新课节开始，逐步添加不同类型的问题，并最终测试和运行这个课程。


---



## 1. 准备工作与创建课程 🛠️



首先，你需要加载 `swirlify` 包。这个包是创建和管理Swirl课程的核心工具。



```r
library(swirlify)
```

`swirlify` 始终知晓你的当前工作目录。为了组织方便，建议为你的Swirl课程创建一个专用目录。例如，你可以在桌面上创建一个名为 `courses` 的文件夹。


```r
setwd("~/Desktop/courses")
```





准备工作完成后，我们可以开始创建新的课程和课节了。


---




## 2. 创建新课节与课程结构 📁


你可以使用 `new_lesson` 函数来同时创建一个新课程和一个新课节。



```r
new_lesson(lesson_name = "Lesson One", course_name = "My First Course")
```


执行这个函数会完成几件事：
1.  它会打开一个YAML文件。所有Swirl课节都是用YAML（一种易于理解的标记语言）编写的。
2.  它会创建课程和课节的文件夹结构。



让我们来看看创建的文件结构。在 `courses` 目录下，现在会有一个名为 `My_First_Course` 的文件夹，里面包含一个名为 `Lesson_One` 的子文件夹。


以下是 `Lesson_One` 文件夹内生成的关键文件：



*   **`customTests.R`**：你可以在这里指定用于测试问题答案正确性的自定义函数。我们稍后会讨论答案测试。
*   **`dependson.txt`**：这是一个文本文件，用于列出本课节依赖的R包。Swirl会在课节开始前检查这些包是否已安装。
*   **`initLesson.R`**：这是一个R脚本。你在这里编写的任何代码都会在课节开始前执行。例如，你可以在这里加载数据，或者创建学生将在课节中用到的函数。
*   **`lesson.yaml`**：这就是我们刚才看到的YAML文件，它是课节内容的核心，所有问题和指令都写在这里。

推荐使用RStudio来编写Swirl课节，因为将文本编辑器和R控制台并排显示在同一屏幕上非常方便。当然，你也可以选择适合自己的工作流程。



---



## 3. 编写课节内容：添加问题 ✍️


现在我们已经设置好了新课节，可以开始添加问题了。`swirlify` 提供了一系列以 `wq_` 开头的函数，用于添加不同类型的问题。



### 添加消息类问题

最简单的题型是“消息”类问题，它只向学生显示信息，不要求输入。使用 `wq_message()` 函数。

```r
wq_message()
```





执行后，`lesson.yaml` 文件中会添加一个消息问题的模板。你可以编辑它，例如：




```yaml
- Class: text
  Output: Welcome to Lesson One.
```

### 添加命令类问题




接下来，让我们添加一个“命令”类问题，它会提示学生在R控制台中输入代码。使用 `wq_command()` 函数。


```r
wq_command()
```




同样，模板会被添加到 `lesson.yaml` 文件中。现在我们来编辑它，创建一个简单的问题：



*   **问题**：`Add 2 and 2 using the plus operator.`
*   **正确答案**：`2 + 2`
*   **答案测试**：`omnitest`。这是一个Swirl自带的函数，用于测试学生输入的答案。80%到90%的情况下你都可以使用它。
*   **提示**：`Type 2 + 2`

编辑后的YAML部分如下所示：




```yaml
- Class: cmd_question
  Output: Add 2 and 2 using the plus operator.
  CorrectAnswer: 2 + 2
  AnswerTests: omnitest(correctExpr='2 + 2')
  Hint: Type 2 + 2.
```


---




## 4. 管理课程清单与测试课节 ✅



编写完问题后，需要将课节添加到课程的清单中。这可以通过 `add_to_manifest()` 函数轻松完成。

```r
add_to_manifest()
```


这个操作会在课程目录（`My_First_Course`）下创建一个 `MANIFEST` 文件。这个文件有两个作用：
1.  记录课程中包含哪些课节。
2.  定义课节显示的顺序。
这样，如果你在课程文件夹中存放了数据或其他文件，它们不会作为可选的课节出现在学生的菜单里，有助于保持项目结构清晰。




现在，是时候测试我们的课节了。

首先，使用 `test_lesson()` 函数来检查课节的格式是否正确。




```r
test_lesson()
```

如果没有收到任何警告或错误信息，说明课节通过了基本的格式检查。




接着，使用 `demo_lesson()` 函数来实际运行这个课节，进行体验。



```r
demo_lesson()
```


这个函数会直接启动你正在编写的课节，无需经过Swirl的常规菜单。你会看到第一个消息：“Welcome to Lesson One.”。然后，会出现命令问题：“Add 2 and 2 using the plus operator.”。输入 `2 + 2` 后，课节便顺利结束。



---


## 总结 📝


本节课中，我们一起学习了创建自定义Swirl课程的基本流程：
1.  使用 `new_lesson()` 初始化课程和课节结构。
2.  了解课节文件夹中的关键文件及其作用。
3.  使用 `wq_message()` 和 `wq_command()` 等函数向 `lesson.yaml` 文件中添加不同类型的问题。
4.  使用 `add_to_manifest()` 管理课程清单。
5.  使用 `test_lesson()` 和 `demo_lesson()` 来测试和运行你的课节。



![](img/6a2e6952a1275290dcddde84e55a3a07_123.png)

你已经掌握了创建交互式R编程教程的基础。接下来，可以尝试添加更多复杂的问题类型（如多选题、图形题等），并利用 `customTests.R` 和 `initLesson.R` 文件来增强课节的功能。