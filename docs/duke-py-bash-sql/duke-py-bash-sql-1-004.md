#  004：Python环境配置入门 🐍

在本节课中，我们将学习如何搭建一个Python项目环境。你将掌握使用PIP工具管理Python库，以及创建和使用虚拟环境来隔离项目依赖。

---

## 概述

一个良好的开发环境是高效编程的基础。本节将引导你完成Python环境配置的核心步骤，包括包管理工具PIP的使用和虚拟环境的创建与管理。

---

## 安装、卸载与更新Python库

![](img/71bd8f0cffb05ac81719a8fa4ce128e0_0.png)

上一节我们了解了环境配置的重要性，本节中我们来看看如何使用PIP（Python包安装程序）来管理第三方库。

PIP是Python的包管理器，用于从Python包索引（PyPI）安装、卸载和更新软件包。其基本命令格式如下：

**安装库：**
```bash
pip install package_name
```

**卸载库：**
```bash
pip uninstall package_name
```

**更新库：**
```bash
pip install --upgrade package_name
```

---

## 使用Requirements文件

手动记录每个依赖库的版本非常繁琐。为此，我们可以使用`requirements.txt`文件来统一管理项目依赖。

以下是`requirements.txt`文件的核心操作：

**生成依赖列表：**
将当前环境中已安装的包及其版本导出到一个文件中。
```bash
pip freeze > requirements.txt
```

**从文件安装依赖：**
在新环境中，可以一键安装文件中列出的所有依赖。
```bash
pip install -r requirements.txt
```

---

## 创建与管理Python虚拟环境

不同的项目可能需要不同版本的库。为了避免冲突，我们需要为每个项目创建独立的虚拟环境。

以下是创建和使用虚拟环境的步骤：

**创建虚拟环境：**
使用`venv`模块创建一个新的隔离环境。`myenv`是环境文件夹的名称，你可以自定义。
```bash
python -m venv myenv
```

**激活虚拟环境：**
激活后，终端提示符通常会变化，表示你已进入该虚拟环境。
- **在Windows上：**
  ```bash
  myenv\Scripts\activate
  ```
- **在macOS/Linux上：**
  ```bash
  source myenv/bin/activate
  ```

**停用虚拟环境：**
完成工作后，可以退出当前虚拟环境，回到系统全局的Python环境。
```bash
deactivate
```

![](img/71bd8f0cffb05ac81719a8fa4ce128e0_2.png)

---

## 总结

本节课中我们一起学习了Python环境配置的核心技能。我们掌握了使用PIP进行库的安装、卸载和更新，学会了通过`requirements.txt`文件管理项目依赖，并实践了创建、激活和停用Python虚拟环境来保持项目间的独立性。这些是开始任何Python数据工程项目前必须掌握的基础。