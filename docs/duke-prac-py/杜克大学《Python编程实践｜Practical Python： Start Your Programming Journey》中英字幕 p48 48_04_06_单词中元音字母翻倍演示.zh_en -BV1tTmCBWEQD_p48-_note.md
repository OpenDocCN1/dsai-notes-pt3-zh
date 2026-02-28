# Python编程实践：48：单词中元音字母翻倍演示

![](img/d7a6dcb68c7a1b0954e51d3bbc5240b9_0.png)

## 概述

在本节课中，我们将学习如何编写一个Python程序，该程序接收用户输入的一个单词，并生成一个新单词。新单词的规则是：将原单词中的所有元音字母（a, e, i, o, u）重复一次，而辅音字母保持不变。我们将通过使用`while`循环、字符串索引和条件判断来实现这个功能。

---

## 问题分析与计划

首先，我们需要明确任务：用户输入一个单词，程序输出一个新单词，其中元音字母出现两次。

在Python中，字符串是不可变的，这意味着我们不能直接修改原始字符串。因此，我们的策略是创建一个新的空字符串，然后遍历原始单词的每个字母，根据字母类型（元音或辅音）决定向新字符串中添加一个还是两个该字母。

以下是我们的解决计划：
1.  向用户请求一个单词。
2.  初始化一个空字符串，用于构建新单词。
3.  使用循环遍历原始单词的每一个字母。
4.  对于每个字母，检查它是否为元音。
5.  如果是元音，则向新字符串添加两个该字母；否则，只添加一个。
6.  循环结束后，打印出构建好的新单词。

---

## 代码实现步骤

### 第一步：获取用户输入

我们使用`input()`函数来获取用户输入的单词，并将其存储在一个变量中。

```python
word = input("Enter a word: ")
```

### 第二步：初始化变量

我们需要两个关键变量：
*   `new_word`：用于累积构建新单词，初始为空字符串。
*   `index`：用于在`while`循环中追踪当前正在处理哪个字母，初始为0。

```python
new_word = ''
index = 0
```

### 第三步：构建循环结构

我们需要一个循环来逐个检查单词中的字母。我们将使用`while`循环，并在每次迭代后更新`index`以指向下一个字母。

循环的停止条件是`index`等于单词的长度（即所有字母都已处理完毕）。因此，循环继续的条件是`index < len(word)`。

```python
while index < len(word):
    # 处理逻辑将放在这里
```

### 第四步：在循环内判断并添加字母

在循环体内，我们使用`word[index]`来获取当前字母。然后判断它是否在元音字符串`"aeiou"`中。

*   如果是元音，我们向`new_word`添加两个该字母。
*   如果不是元音（即辅音），我们只添加一个该字母。

```python
while index < len(word):
    if word[index] in "aeiou":
        new_word = new_word + word[index] * 2
    else:
        new_word = new_word + word[index]
```

### 第五步：更新索引并完成循环

上一节我们介绍了如何在循环内处理字母，但要使循环正确推进，关键的一步是在每次处理完一个字母后，将`index`的值增加1，以便下次循环检查下一个字母。如果忘记这一步，程序将陷入无限循环。

```python
while index < len(word):
    if word[index] in "aeiou":
        new_word = new_word + word[index] * 2
    else:
        new_word = new_word + word[index]
    index = index + 1  # 关键步骤：移动到下一个字母
```

### 第六步：输出结果

循环结束后，`new_word`已经构建完成，我们将其打印出来。

```python
print("New word is", new_word)
```

---

## 完整代码与测试

将以上所有步骤组合起来，就得到了完整的程序。

```python
# 1. 获取用户输入
word = input("Enter a word: ")

# 2. 初始化变量
new_word = ''
index = 0

# 3. 循环处理每个字母
while index < len(word):
    # 4. 判断是否为元音并相应添加字母
    if word[index] in "aeiou":
        new_word = new_word + word[index] * 2
    else:
        new_word = new_word + word[index]
    # 5. 更新索引，准备处理下一个字母
    index = index + 1

# 6. 输出最终结果
print("New word is", new_word)
```

现在，让我们测试几个例子：
*   输入 `celebrate`，输出 `ceeleebbraatee`。
*   输入 `progress`，输出 `proogreess`。
*   输入 `bookmobile`，输出 `boookmobiilee`。
*   输入 `shy`，输出 `shy`。

---

## 总结

本节课中我们一起学习了如何构建一个字符串处理程序。我们掌握了以下核心技能：
1.  使用`while`循环和索引变量`index`来遍历字符串。
2.  使用`in`关键字检查一个字符是否存在于某个字符串中（例如判断元音）。
3.  使用字符串拼接（`+`）和重复（`*`）操作来构建新的字符串。
4.  理解了在循环中更新控制变量（如`index`）的重要性，以避免无限循环。

这个程序的核心逻辑可以推广到许多其他字符串处理任务中，例如替换特定字符、统计字母出现次数或实现简单的加密解密。你可以尝试修改代码，例如让辅音字母翻倍，或者处理大写字母，来进一步巩固所学知识。

![](img/d7a6dcb68c7a1b0954e51d3bbc5240b9_2.png)

![](img/d7a6dcb68c7a1b0954e51d3bbc5240b9_4.png)

Happy programming! 🎉