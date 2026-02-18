# 20：Python中的for循环与列表 🐍

![](img/cd35fe433fdb17fb80a98ed1eb324517_0.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_2.png)

在本节课中，我们将学习Python中的**for循环**和**列表**。我们将首先介绍这两个核心概念是什么，然后通过实际代码演示如何创建和使用它们。



![](img/cd35fe433fdb17fb80a98ed1eb324517_4.png)

## 什么是for循环？ 🔄

![](img/cd35fe433fdb17fb80a98ed1eb324517_6.png)

上一节我们介绍了课程目标，本节中我们来看看for循环。for循环用于**顺序遍历**，即按顺序访问一系列元素。它们是为此目的而设计的循环结构。



for循环可以遍历一个范围内的值。Python允许`else`关键字与for循环和while循环结合使用。`else`代码块可以放在循环体之后，其中的语句将在循环的所有迭代完成后执行。



![](img/cd35fe433fdb17fb80a98ed1eb324517_8.png)

## 什么是列表？ 📋

了解了for循环后，本节我们来认识列表。请注意，关于列表的更多内容将在课程2中深入讲解。目前，我们只介绍基本概念。

列表是一种**可变的、有序的**数据序列，由值或元素组成。列表可以被索引，这意味着你可以根据索引值访问列表中的每个元素。

![](img/cd35fe433fdb17fb80a98ed1eb324517_10.png)

列表可以包含**不同数据类型**的项，也可以包含**相同数据类型**的项，这使其功能非常强大。创建一个列表，你只需要使用方括号`[]`。



## 代码演示 💻

![](img/cd35fe433fdb17fb80a98ed1eb324517_12.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_13.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_14.png)

现在，让我们通过代码示例来实践上述概念。



![](img/cd35fe433fdb17fb80a98ed1eb324517_16.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_17.png)

### 示例1：基本的for循环

在下面的脚本中，我首先创建了一个for循环，指定我希望它执行22次迭代。这就是为什么我创建了一个变量`n`，并将其设置为22。

```python
n = 22
for index in range(0, n):
    print(index)
```

![](img/cd35fe433fdb17fb80a98ed1eb324517_19.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_20.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_21.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_22.png)

现在创建for循环。对于在范围0到`n`之间的每一个索引，我们将打印出该索引的值。



![](img/cd35fe433fdb17fb80a98ed1eb324517_23.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_24.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_25.png)

需要记住的是，当我们使用`range`函数时，我们的意思是从0到22范围内的每一个整数或索引，我们都想打印出来。但使用`range`时必须理解，`range`会从起始索引打印到`n-1`索引。因此，它将从0开始，一直迭代到21。



这一点你以后要始终牢记。当我们从0开始计数到21时，我们仍然在处理22个整数值，只是我们从0开始，到达的是第`n-1`个元素。



![](img/cd35fe433fdb17fb80a98ed1eb324517_27.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_28.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_29.png)

所以在这里你可以看到，我从0开始打印出每一个索引，并在21结束，因为它是22减1的索引值，即21。



### 示例2：指定范围的for循环

![](img/cd35fe433fdb17fb80a98ed1eb324517_31.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_32.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_33.png)

接下来看另一个例子，这能解释我之前提到的内容。

![](img/cd35fe433fdb17fb80a98ed1eb324517_35.png)

假设我想从整数值5迭代到11。

![](img/cd35fe433fdb17fb80a98ed1eb324517_37.png)

```python
for i in range(5, 12):
    print(i)
```

![](img/cd35fe433fdb17fb80a98ed1eb324517_39.png)

这里的意思是，对于在范围5到12内的每一个索引`i`，打印索引值。这将输出5到12减1的值，因为请记住，我们访问的是第`n-1`个元素的值。



![](img/cd35fe433fdb17fb80a98ed1eb324517_40.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_41.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_42.png)

所以它会打印5, 6, 7, 8, 9, 10, 11。现在，如果我们想把12也包括进来。



![](img/cd35fe433fdb17fb80a98ed1eb324517_44.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_45.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_46.png)

我们只需要将这个值加1，因为我们访问的是第`n-1`个元素，所以必须把12增加到13。现在如果我运行这个。



你可以在这里看到，索引值是5, 6, 7, 8, 9, 10, 11, 12。12现在被包含在内了。



![](img/cd35fe433fdb17fb80a98ed1eb324517_48.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_49.png)

### 示例3：遍历列表

![](img/cd35fe433fdb17fb80a98ed1eb324517_51.png)

现在让我们遍历一个水果列表。如前所述，列表是一种可以存储值的数据结构。在我们的列表中，有字符串值。

![](img/cd35fe433fdb17fb80a98ed1eb324517_53.png)

列表中有字符串“apples”、“oranges”、“bananas”和“grapes”。

![](img/cd35fe433fdb17fb80a98ed1eb324517_55.png)

```python
fruits = ["apples", "oranges", "bananas", "grapes"]
for fruit in fruits:
    print("The fruit purchased are", fruit)
```

在我们的for循环中，我们说对于水果列表中的每一个水果。

![](img/cd35fe433fdb17fb80a98ed1eb324517_57.png)

我们想打印“The fruit purchased are”，然后我们将访问那个水果。在这种情况下，购买的水果是苹果。购买的水果是橙子。它将为列表中的每一个元素打印这个。



![](img/cd35fe433fdb17fb80a98ed1eb324517_58.png)

这就是循环如此有用的原因。相比于必须访问列表中的每个元素并写一条打印语句，总共写一、二、三、四次，甚至如果你的列表更大，要写更多次，你可以直接使用一个for循环，基本上用两行代码就能遍历列表中的每个元素并为你打印出来，而不是写那么多行做同样事情的代码。



![](img/cd35fe433fdb17fb80a98ed1eb324517_60.png)

这就是为什么循环如此强大，它们可以帮助你节省时间，避免编写重复的代码行，从而写出更强大、更优化的程序。



![](img/cd35fe433fdb17fb80a98ed1eb324517_61.png)

## 总结 📝

![](img/cd35fe433fdb17fb80a98ed1eb324517_63.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_64.png)

本节课中我们一起学习了Python中的**for循环**和**列表**。我们了解了for循环用于顺序遍历，列表是可变的有序序列。通过多个代码示例，我们实践了如何使用`range()`函数进行迭代，以及如何遍历列表中的元素。掌握这些基础概念对于编写高效、简洁的Python代码至关重要。