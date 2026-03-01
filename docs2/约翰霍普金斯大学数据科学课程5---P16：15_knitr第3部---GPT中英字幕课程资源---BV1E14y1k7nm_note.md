# 课程5：《可重复研究》｜第16课：knitr 第3部分 📝

![](img/2d93f7847e8d09b57dcd69ff7684624f_0.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_0.png)

在本节课中，我们将学习如何创建一个基础的 knitr 文档。我们将重点介绍在 RStudio 环境中创建的方法，因为这是最简单的方式。当然，这并非 RStudio 的专属功能，但我们将以此为例进行演示。

![](img/2d93f7847e8d09b57dcd69ff7684624f_2.png)

## 创建基础 knitr 文档 🚀

![](img/2d93f7847e8d09b57dcd69ff7684624f_3.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_4.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_5.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_6.png)

上一节我们介绍了 knitr 的基本概念，本节中我们来看看如何实际操作。

在 RStudio 中，点击左上角的“新建文档”按钮，你会看到多个选项。选择“R Markdown”选项，即可创建一个新的 R Markdown 文件。

![](img/2d93f7847e8d09b57dcd69ff7684624f_2.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_3.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_4.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_5.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_6.png)

这个新文件将包含你的文本和代码。R Markdown 本质上是嵌入了 R 代码的 Markdown 文档。

![](img/2d93f7847e8d09b57dcd69ff7684624f_8.png)

以下是一个基础的 R Markdown 文档示例。你可以看到，一个特殊的符号表示代码块的开始。

![](img/2d93f7847e8d09b57dcd69ff7684624f_9.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_10.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_11.png)

```r
# 这是一个代码块示例
set.seed(123)
x <- rnorm(100)
mean(x)
```

![](img/2d93f7847e8d09b57dcd69ff7684624f_12.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_13.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_14.png)

具体来说，三个反引号 ```` ``` ```` 后跟花括号 `{r}` 表示一个 R 代码块的开始。在上面的例子中，有三行 R 代码：设置随机种子、生成一些随机正态变量、计算均值。代码块以三个反引号结束。

![](img/2d93f7847e8d09b57dcd69ff7684624f_8.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_9.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_10.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_11.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_12.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_13.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_14.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_16.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_17.png)

在这个带阴影的代码区域上方，是文本内容。例如，标题是“我的第一个 knitr 文档”，接着是一行文本“这是一些文字”，然后是“这是一个代码块”的说明，之后才开始代码块。

![](img/2d93f7847e8d09b57dcd69ff7684624f_18.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_16.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_17.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_18.png)

## 处理文档与生成输出 🔄

在 RStudio 中，你将同时看到代码块和文本块。我们的目标是处理这个 knitr 文档，生成人类可读的输出。这意味着你需要运行 R 代码，执行这三行命令，然后将 R 代码的输出结果嵌入到你的文档中。

这段 R 代码的输出是什么？它只做了一件事：计算均值。因此，它会生成该模拟数据集的均值。

![](img/2d93f7847e8d09b57dcd69ff7684624f_20.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_21.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_22.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_20.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_21.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_22.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_23.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_24.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_25.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_26.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_23.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_24.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_25.png)

在 RStudio 中，这非常简单。你只需点击“Knit HTML”按钮，它会自动为你运行所有内容。

![](img/2d93f7847e8d09b57dcd69ff7684624f_26.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_28.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_28.png)

## 在 RStudio 之外使用 knitr 💻

如果你不使用 RStudio，也可以通过以下方式操作。

以下是具体步骤：
1.  使用 `library` 函数加载 knitr 包：`library(knitr)`。
2.  确保你的工作目录设置为 R Markdown 文档所在的位置。
3.  R Markdown 文档通常具有 `.Rmd` 扩展名（大写或小写均可）。这不是必须的，但有助于识别这类文件。
4.  如果你想创建一个网页，可以使用 `knit2html` 函数。

![](img/2d93f7847e8d09b57dcd69ff7684624f_30.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_31.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_32.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_30.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_31.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_32.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_33.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_34.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_33.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_34.png)

`knit2html` 函数会自动处理 R Markdown 文件，运行其中的 R 代码，并将输出结果放入文件中。在 R 中，如果你想在网页浏览器中打开这个文件，可以使用 `browseURL` 函数。

具体来说，`knit2html` 函数会读取你的 R Markdown 文档，创建一个同名的 HTML 文件，然后你就可以在浏览器中打开了。

![](img/2d93f7847e8d09b57dcd69ff7684624f_36.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_37.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_38.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_39.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_36.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_37.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_38.png)

## 查看输出结果 📄

![](img/2d93f7847e8d09b57dcd69ff7684624f_39.png)

这是你将得到的输出，即 HTML 格式的结果。你可以看到大标题、一些常规文本。代码显示在带阴影的框中，而代码的输出结果直接显示在下方。例如，均值是 0.1089，这来自 `mean` 函数的输出。

![](img/2d93f7847e8d09b57dcd69ff7684624f_41.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_42.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_43.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_44.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_41.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_42.png)

## knitr 的工作原理 ⚙️

![](img/2d93f7847e8d09b57dcd69ff7684624f_43.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_44.png)

那么，这里发生了什么？knitr 会获取你原始的 R Markdown 文档（如左侧所示），并将其处理成一个常规的 Markdown 文档。

你可以看到，其中一件事是它获取你的代码，并在常规 Markdown 文档中重现这些代码。但在 Markdown 文档中，它多做了一件事：将 R 代码的评估结果（显示在底部）添加到了 Markdown 文档中。这是在评估 R 代码之后完成的。

![](img/2d93f7847e8d09b57dcd69ff7684624f_46.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_47.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_48.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_49.png)
![](img/2d93f7847e8d09b57dcd69ff7684624f_50.png)

## 重要注意事项与技巧 📌

![](img/2d93f7847e8d09b57dcd69ff7684624f_46.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_47.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_48.png)

了解基本流程后，我们需要注意一些关键点。

![](img/2d93f7847e8d09b57dcd69ff7684624f_49.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_50.png)

首先，当你在 RStudio 中创建新的 knitr 文档时，它会用一些通用的填充文本预填充该文档。你可能想做的第一件事就是删除这些文本，因为它们很可能与你想要做的内容无关。

关于代码块，它们以三个反引号和花括号 `{r}` 开始，并以三个反引号结束。

![](img/2d93f7847e8d09b57dcd69ff7684624f_52.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_52.png)

你所有的 R 代码都放在这些标记之间。现在，你可以有多个代码块，数量不限。你不必将所有 R 代码都放在一个代码块中。但是，任何你有的 R 代码都必须放在由三个反引号指示的代码块中。

你可以为代码块命名。在花括号内的 `r` 后面，你可以立即放一个名字，可以是任何你想要的，然后以花括号结束。

![](img/2d93f7847e8d09b57dcd69ff7684624f_54.png)

![](img/2d93f7847e8d09b57dcd69ff7684624f_54.png)

默认情况下，代码块中的代码会在输出文档中回显。就像在 HTML 文档中看到的那样，它回显了代码，然后给出了该代码的结果。默认情况下，所有代码块中的代码都将在文档中可见。

## 总结 ✨

本节课中，我们一起学习了如何创建基础的 knitr 文档。我们从在 RStudio 中创建 R Markdown 文件开始，了解了其基本结构，即文本与嵌入的 R 代码块相结合。我们演示了如何通过点击按钮或使用 `knit2html` 函数来处理文档，从而生成包含代码及其运行结果的可读输出（如 HTML 网页）。我们还探讨了 knitr 的工作原理，即将 R Markdown 转换为包含代码输出的标准 Markdown，并掌握了一些实用技巧，如删除模板文本、使用多个代码块以及为代码块命名。掌握这些是进行可重复研究文档编写的重要一步。