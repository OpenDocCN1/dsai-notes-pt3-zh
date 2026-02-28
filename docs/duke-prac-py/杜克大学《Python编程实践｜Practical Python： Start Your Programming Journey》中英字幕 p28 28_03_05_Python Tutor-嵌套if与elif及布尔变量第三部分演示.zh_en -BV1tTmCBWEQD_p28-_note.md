# Python编程实践：嵌套if与elif及布尔变量

![](img/cfcc8cc5b5e476774ee607beb00a6b58_0.png)

## 概述
在本节课中，我们将学习如何使用布尔变量和嵌套if语句来编写更复杂的Python程序。

## 创建布尔变量
首先，我们需要创建一个布尔变量来表示鱼是否为成鱼。

```python
size_is_adult = input("Enter A for adult fish and B for baby fish").upper() == 'A'
```

这里，我们使用`input()`函数获取用户输入，并将其转换为大写字母。然后，我们比较输入是否等于'A'，如果等于，则`size_is_adult`变量被设置为`True`，否则为`False`。

## 更新代码
接下来，我们需要在代码中更新所有使用`size`变量的地方，以使用新的布尔变量`size_is_adult`。

```python
if size_is_adult:
    print("It's an adult fish.")
else:
    print("It's a baby fish.")
```

这里，我们使用`if`语句检查`size_is_adult`变量的值。如果为`True`，则打印“它是成鱼”，否则打印“它是幼鱼”。

## 使用布尔变量进行决策
布尔变量可以用于在代码中进行更复杂的决策。

```python
if size_is_adult:
    print("It's an adult fish.")
else:
    print("It's a baby fish.")
```

这里，我们使用布尔变量`size_is_adult`来决定打印哪条消息。

![](img/cfcc8cc5b5e476774ee607beb00a6b58_2.png)

## 总结
本节课中，我们学习了如何使用布尔变量和嵌套if语句来编写更复杂的Python程序。通过创建布尔变量和更新代码，我们可以使程序更加灵活和可读。