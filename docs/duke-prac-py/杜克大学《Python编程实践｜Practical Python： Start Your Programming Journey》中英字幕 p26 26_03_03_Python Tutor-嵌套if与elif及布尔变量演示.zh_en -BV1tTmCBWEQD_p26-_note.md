# Python编程实践：嵌套if与elif及布尔变量演示

![](img/17bd39ff29d745b7f3ce984837df6a9d_0.png)

在本节课中，我们将学习如何使用嵌套if语句和elif语句来处理更复杂的条件判断，并了解布尔变量的使用。

## 1. 问题背景

假设我们有一个鱼缸，需要购买一些鱼，然后我们会去鱼店。我们将编写一个程序来计算鱼的总价。通常情况下，购买鱼时不会只买一条，所以我们需要进行一些计算来得出总价。

我们将保持程序简单，只关注两种鱼：金鱼和天使鱼。金鱼的复数形式是guuppies，而天使鱼的复数形式仍然是angelfish。对于每种鱼，购买成年鱼和幼年鱼的价格不同。

## 2. 程序设计

为了实现这个程序，我们需要完成以下步骤：

1. **获取输入**：询问用户想要购买哪种鱼（金鱼或天使鱼）、鱼的类型（成年鱼或幼年鱼）以及购买数量。
2. **计算总价**：根据用户选择的鱼种、类型和数量，计算总价。
3. **输出结果**：打印出购买鱼的总价，并包含鱼的种类、数量和类型等信息。

## 3. 代码实现

```python
# 定义鱼的价格
adult_angel_fish_price = 5.0
baby_angel_fish_price = 0.5
adult_guppy_price = 3.0
baby_guppy_price = 0.1

# 获取用户输入
species = input("请输入鱼种（guppy或angelfish）：")
size = input("请输入鱼的类型（A为成年鱼，B为幼年鱼）：")
number = int(input("请输入购买数量："))

# 计算总价
total = 0.0
if species == "angelfish":
    if size == "A":
        total = adult_angel_fish_price * number
    elif size == "B":
        total = baby_angel_fish_price * number
elif species == "guppy":
    if size == "A":
        total = adult_guppy_price * number
    elif size == "B":
        total = baby_guppy_price * number
else:
    print("抱歉，我们没有这种鱼。")

# 输出结果
if species == "angelfish":
    if size == "A":
        print(f"购买{number}条成年天使鱼，总价为：{total}美元")
    elif size == "B":
        print(f"购买{number}条幼年天使鱼，总价为：{total}美元")
elif species == "guppy":
    if size == "A":
        print(f"购买{number}条成年金鱼，总价为：{total}美元")
    elif size == "B":
        print(f"购买{number}条幼年金鱼，总价为：{total}美元")
```

## 4. 总结

![](img/17bd39ff29d745b7f3ce984837df6a9d_2.png)

本节课中，我们学习了如何使用嵌套if语句和elif语句来处理更复杂的条件判断，并了解了布尔变量的使用。通过编写一个简单的鱼店购买程序，我们掌握了如何根据用户输入计算总价，并输出相关信息。