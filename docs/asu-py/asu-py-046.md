# 46：Python 多态性功能演示 🚗


在本节课中，我们将通过创建一个包含继承关系的类结构，来演示 Python 中多态性的工作原理。我们将创建一个基础的 `Vehicle` 类，并从中派生出 `Car` 和 `Truck` 子类，展示同名方法如何在不同类中表现出不同的行为。



---




## 概述




多态性是面向对象编程的核心概念之一，它允许我们使用统一的接口来操作不同的对象。在本演示中，我们将通过一个车辆类的例子，具体展示子类如何重写父类的方法，以及 Python 如何根据对象的实际类型来调用相应的方法。


---



## 创建基类：Vehicle 🚙



首先，我们创建一个名为 `Vehicle` 的基类。这个类将定义所有车辆共有的基本属性和方法。



以下是 `Vehicle` 类的代码：



```python
class Vehicle:
    def __init__(self, name, color):
        self.name = name
        self.color = color

    def speed(self):
        return "Max speed is unknown."

    def gears(self):
        return "Number of gears is unknown."

    def details(self):
        return f"Name: {self.name}, Color: {self.color}"
```



在这个类中，我们定义了：
*   **构造函数 `__init__`**：用于初始化车辆的 `name`（名称）和 `color`（颜色）。
*   **方法 `speed` 和 `gears`**：返回关于速度和档位的通用信息。
*   **方法 `details`**：返回车辆的名称和颜色信息。




---



## 创建子类：Car 🏎️



上一节我们介绍了基类 `Vehicle`，本节中我们来看看如何创建第一个子类 `Car`。`Car` 类将继承 `Vehicle` 的所有属性和方法，并重写 `speed` 和 `gears` 方法以提供具体信息。



以下是 `Car` 类的代码：




```python
class Car(Vehicle):
    def __init__(self, name, color):
        super().__init__(name, color)

    def speed(self):
        return "Top speed is 140."

    def gears(self):
        return "Maximum number of gears is 6."

    def details(self):
        parent_details = super().details()
        return f"{parent_details}\nGears: {self.gears()}\nSpeed: {self.speed()}"
```



在 `Car` 类中：
*   我们使用 `super().__init__(name, color)` 来调用父类的构造函数。
*   我们重写了 `speed` 和 `gears` 方法，返回汽车特定的值。
*   在 `details` 方法中，我们先调用父类的 `details` 方法获取基本信息，再追加子类特有的档位和速度信息。这体现了多态性：同名方法 `details` 在父类和子类中有不同的实现。



---



## 创建另一个子类：Truck 🚚



同样地，我们可以创建另一个子类 `Truck`。它也将继承自 `Vehicle`，但拥有与 `Car` 不同的属性值。




以下是 `Truck` 类的代码：




```python
class Truck(Vehicle):
    def __init__(self, name, color):
        super().__init__(name, color)

    def speed(self):
        return "Top speed is 120."

    def gears(self):
        return "Maximum number of gears is 8."

    def details(self):
        parent_details = super().details()
        return f"{parent_details}\nGears: {self.gears()}\nSpeed: {self.speed()}"
```


`Truck` 类的结构与 `Car` 类相似，但速度和档位的数值不同，这进一步展示了多态性：相同的接口（方法名）因对象类型不同而产生不同的结果。



---



## 演示多态性行为



现在，让我们创建对象并观察多态性是如何工作的。



以下是创建对象并调用方法的代码：








```python
# 创建 Car 对象
my_car = Car("Corolla", "blue")
print(my_car.details())
print()  # 打印空行分隔
# 创建 Truck 对象
my_truck = Truck("Titan", "black")
print(my_truck.details())
```



当我们运行这段代码时，输出如下：






```
Name: Corolla, Color: blue
Gears: Maximum number of gears is 6.
Speed: Top speed is 140.
Name: Titan, Color: black
Gears: Maximum number of gears is 8.
Speed: Top speed is 120.
```



**关键观察点：**
1.  **方法解析顺序**：当调用 `my_car.details()` 时，Python 首先在 `Car` 类中寻找 `details` 方法。如果找到，就执行它；如果没找到，则会去父类 `Vehicle` 中寻找。
2.  **多态性的体现**：`Car` 和 `Truck` 对象都调用了名为 `details` 的方法，但由于它们属于不同的类，因此执行了各自类中的 `details` 方法实现，输出了不同的具体信息。
3.  **`super()` 的作用**：在子类的 `details` 方法中，我们使用 `super().details()` 调用了父类的方法，从而复用了获取名称和颜色的代码，然后在此基础上添加了子类特有的信息。



---

## 总结





本节课中我们一起学习了 Python 中多态性的一个具体演示。我们通过以下步骤实现了多态：


1.  创建了一个基类 `Vehicle`，定义了通用的属性和方法。
2.  创建了 `Car` 和 `Truck` 两个子类，它们继承自 `Vehicle`。
3.  在子类中重写了父类的方法（如 `speed`, `gears`, `details`），为不同类型的车辆提供了特定的行为。
4.  通过创建对象并调用同名方法，观察到 Python 会根据对象的实际类型自动选择正确的方法版本执行。



![](img/abfb53213e7895e945b2354984480484_132.png)

多态性使得代码更加灵活和可扩展。我们可以编写通用的代码来处理父类对象，而这些代码同样可以无缝地应用于任何子类对象，每个子类对象会表现出符合自身特性的行为。这是构建大型、可维护面向对象程序的重要基石。