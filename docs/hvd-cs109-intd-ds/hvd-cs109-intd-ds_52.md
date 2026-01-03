# 第三十七章 访问终端和安装 Git

> 原文：[`rafalab.dfci.harvard.edu/dsbook/accessing-the-terminal-and-installing-git.html`](https://rafalab.dfci.harvard.edu/dsbook/accessing-the-terminal-and-installing-git.html)

在开始之前，我们需要确保你可以访问 *终端* 并且 Git 已经安装。终端集成在 Mac 和 Linux 系统中，但 Windows 用户将需要安装一个 *模拟器*。有许多模拟器选项可用，但在这里我们展示如何安装 Git Bash，因为它可以作为 Windows Git 安装的一部分来完成。由于 Mac 和 Windows 之间的差异，本章的章节根据这些差异进行了划分。

## 37.1 在 Mac 上访问终端

在第三十八章中，我们描述了终端是如何成为我们进入 Unix 世界窗口的。在 Mac 上，你可以通过打开实用工具文件夹中的应用程序来访问终端：

![](img/a3efa812bf0fab4f10f5e33556ecedee.png)![](img/252b735511d4a193457961eb2ecb2e0a.png)![](img/76ad97e5444cfe53d301596e2af94486.png)

你也可以使用 Mac 上的 Spotlight 功能，通过按 command-spacebar，然后输入 *终端*。

另一种访问终端的方式是通过 RStudio。在 *控制台* 面板中，你应该能看到一个 *终端* 选项卡。如果你点击这个选项卡，你将打开一个终端窗口。

## 37.2 在 Mac 上安装 Git

**警告：本小节中的说明不适用于 Windows 用户。**

1.  首先按照上一节所述打开终端。

1.  一旦启动终端，你会看到一个类似这样的控制台：

![](img/76ad97e5444cfe53d301596e2af94486.png)

1.  你可能已经安装了 Git。一种检查方法是通过输入以下内容来请求版本：

```r
git --version
```

如果你得到了版本号，说明它已经安装了。如果没有，你会得到以下信息：

![](img/676ba9e4ed2712ff722126c85638893c.png)

你将被询问是否要安装它。你应该点击 *安装*：

![](img/eba7dcc2063f973a341f3f94e80c3fb2.png)

1.  这将带你完成安装过程：

![](img/5bf5e763947a243dffec06d66dfaeba8.png)![](img/a531aad58c4a979b0c71e1fe4f4131f9.png)![](img/83bc2792b2c4669e7cb64b80a4f31a5a.png)

1.  安装完成后，你可以再次检查版本，它应该会显示类似以下内容：

![](img/14c32f8dc47daea5d6ce03758fae9464.png)

恭喜你。你已经在你的 Mac 上安装了 Git。

## 37.3 在 Windows 上安装 Git 和 Git Bash

**警告：本小节中的说明不适用于 Mac 用户。**

有几种软件允许你在 Windows 上执行 Unix 命令。我们将使用 Git Bash，因为它与 RStudio 兼容，并且当我们在 Windows 上安装 Git 时会自动安装。

1.  首先在浏览器中搜索 *Git for Windows* 并点击来自 *git-scm.com* 的链接。

![](img/c0f91ab26dcc1627bd4194c5c49773a0.png)

1.  这将带您到 *下载 Git* 页面，您可以从该页面下载 *最新维护版本*：

![图片](img/014d101821c153ed3871b76198fae4fc.png)

1.  您可以接受运行安装程序并同意许可协议：

![图片](img/5a9fe3461d0200823a459f417b730a6e.png)![图片](img/63c39439925f1ae756bc0ff60b8a7165.png)

1.  在安装步骤之一中，您将被要求选择 Git 的默认编辑器。除非您已经是 *vi* 或 *vim* 用户，否则我们建议不要选择 *vim*，它可能是默认选项。如果您在提供的选项中不认识您熟悉的编辑器，我们建议您选择 *nano* 作为 Git 的默认编辑器，因为它最容易学习：

![图片](img/8d831bad51fd62461d6d34f7679d9aaa.png)

1.  下一个安装决策实际上是一个 **重要** 的决策。此安装过程安装 Git Bash。我们建议您选择 *从 Windows 命令提示符安装 Git 和可选的 Unix 工具*，这样您就可以在 RStudio 中学习 Unix。然而，如果您这样做，**一些在您的 Windows 命令行上运行的命令将停止工作**。如果您不使用您的 Windows 命令行，那么这应该不会是问题。此外，大多数，如果不是所有，这些 Windows 命令行都有一个 Unix 等价物，您现在可以使用。

![图片](img/9f39a55463dd37ab44636282444ae01a.png)

1.  您现在可以继续选择默认选项。

![图片](img/dd43b561e7aa6ac495f97f8907137747.png)![图片](img/8f112e4cf68e9ef2c34087d8ed20f903.png)![图片](img/d9cfa8427a664ec9c0f015391221cd04.png)

![图片](img/21bd2fca89d3ea875943338aa3cedf09.png)![图片](img/5e370231e2e0cc79e85832e222eb5264.png)

您现在已在 Windows 上安装了 Git。

## 37.4 在 Windows 上访问终端

现在 Git Bash 已安装，我们可以通过 RStudio 或直接打开 Git Bash 来访问终端。

要通过 RStudio 访问终端，我们需要更改一个首选项，以便 Git Bash 成为 RStudio 中的默认 Unix shell。在 RStudio 中，转到首选项（位于文件下拉菜单下），然后选择 *终端*，然后选择 *Git Bash*：

![图片](img/5688eefb2dfae0ad4c16425eb06d973e.png)

要检查您实际上是否在 RStudio 中使用 Git Bash，您可以在 RStudio 中打开一个 *新终端*：

![图片](img/c034726c5c3754794eaa9c116924756e.png)

它应该看起来像这样：

![图片](img/caa4531ed5e7f9f47f25fb36416fc713.png)

通常我们想要访问终端，但不需要 RStudio。您可以通过直接运行 Git Bash 程序来实现这一点：

![图片](img/ff2ce9186a12ad7342b296d173a7da7f.png)![图片](img/e7d2f88592356f71f1a7b55986929d57.png)
