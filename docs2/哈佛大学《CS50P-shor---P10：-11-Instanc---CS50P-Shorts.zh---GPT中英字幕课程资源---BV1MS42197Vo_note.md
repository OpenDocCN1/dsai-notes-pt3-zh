# 哈佛大学《CS50P Python编程入门》短课程 - P10：实例变量 📦

![](img/7b25470d5570a713bd45dd40288765bd_0.png)

在本节课中，我们将要学习面向对象编程中的一个核心概念：**实例变量**。我们将通过一个“包裹”类的例子，理解如何为类的每个独立对象存储和访问其特有的数据。

![](img/7b25470d5570a713bd45dd40288765bd_2.png)

![](img/7b25470d5570a713bd45dd40288765bd_3.png)

![](img/7b25470d5570a713bd45dd40288765bd_4.png)

![](img/7b25470d5570a713bd45dd40288765bd_5.png)

---

## 概述

在之前关于定义类的短课程中，我们学习了如何创建一个类作为对象的模板。本节课，我们将深入探讨如何为这个模板创建的每个具体对象（即实例）赋予其独有的属性，这些属性被称为**实例变量**。

![](img/7b25470d5570a713bd45dd40288765bd_7.png)

![](img/7b25470d5570a713bd45dd40288765bd_8.png)

![](img/7b25470d5570a713bd45dd40288765bd_9.png)

![](img/7b25470d5570a713bd45dd40288765bd_10.png)

![](img/7b25470d5570a713bd45dd40288765bd_11.png)

---

![](img/7b25470d5570a713bd45dd40288765bd_12.png)

![](img/7b25470d5570a713bd45dd40288765bd_13.png)

![](img/7b25470d5570a713bd45dd40288765bd_14.png)

![](img/7b25470d5570a713bd45dd40288765bd_15.png)

## 回顾：创建类和实例

![](img/7b25470d5570a713bd45dd40288765bd_17.png)

首先，我们来回顾一下如何定义一个简单的类并创建其实例。我们定义了一个名为 `Package` 的类，它代表一个包裹。

![](img/7b25470d5570a713bd45dd40288765bd_18.png)

![](img/7b25470d5570a713bd45dd40288765bd_19.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight
```

![](img/7b25470d5570a713bd45dd40288765bd_21.png)

![](img/7b25470d5570a713bd45dd40288765bd_22.png)

在上面的代码中，`__init__` 是一个特殊的方法（构造器），当我们创建类的新实例时，Python会自动调用它。

![](img/7b25470d5570a713bd45dd40288765bd_23.png)

![](img/7b25470d5570a713bd45dd40288765bd_24.png)

---

## 理解 `__init__` 方法和 `self`

![](img/7b25470d5570a713bd45dd40288765bd_26.png)

上一节我们介绍了类的定义，本节中我们来看看 `__init__` 方法的具体工作。

![](img/7b25470d5570a713bd45dd40288765bd_27.png)

![](img/7b25470d5570a713bd45dd40288765bd_28.png)

![](img/7b25470d5570a713bd45dd40288765bd_29.png)

![](img/7b25470d5570a713bd45dd40288765bd_30.png)

![](img/7b25470d5570a713bd45dd40288765bd_31.png)

当我们执行类似 `package1 = Package(1, "Alice", "Bob", 10)` 的代码时，会发生以下事情：
1.  Python创建一个新的 `Package` 类实例。
2.  自动调用 `__init__` 方法。
3.  参数 `self` 被自动传递给 `__init__`，它指向**正在创建的这个新实例**。
4.  我们传入的其他参数（`1`, `"Alice"`, `"Bob"`, `10`）被分别赋值给 `self.number`, `self.sender` 等。

![](img/7b25470d5570a713bd45dd40288765bd_32.png)

![](img/7b25470d5570a713bd45dd40288765bd_33.png)

![](img/7b25470d5570a713bd45dd40288765bd_34.png)

这里的 `self.number`、`self.sender` 等，就是**实例变量**。它们属于类的某个特定实例，每个实例都拥有自己独立的一套这些变量。

---

![](img/7b25470d5570a713bd45dd40288765bd_36.png)

![](img/7b25470d5570a713bd45dd40288765bd_37.png)

## 访问实例变量

![](img/7b25470d5570a713bd45dd40288765bd_38.png)

![](img/7b25470d5570a713bd45dd40288765bd_39.png)

![](img/7b25470d5570a713bd45dd40288765bd_40.png)

![](img/7b25470d5570a713bd45dd40288765bd_41.png)

理解了实例变量是如何被设置的之后，我们来看看如何访问和使用它们。

![](img/7b25470d5570a713bd45dd40288765bd_43.png)

![](img/7b25470d5570a713bd45dd40288765bd_44.png)

我们可以通过 `实例.变量名` 的格式来访问实例变量。例如，如果我们有一个 `Package` 类的实例 `package1`，那么 `package1.number` 就存储了它的编号。

![](img/7b25470d5570a713bd45dd40288765bd_46.png)

以下是一个演示如何创建多个包裹并访问其实例变量的完整示例：

![](img/7b25470d5570a713bd45dd40288765bd_47.png)

![](img/7b25470d5570a713bd45dd40288765bd_48.png)

![](img/7b25470d5570a713bd45dd40288765bd_49.png)

```python
# 定义Package类
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight

# 创建两个包裹实例
package1 = Package(1, "Alice", "Bob", 10)
package2 = Package(2, "Bob", "Charlie", 15)

# 将实例放入列表
packages = [package1, package2]

![](img/7b25470d5570a713bd45dd40288765bd_51.png)

![](img/7b25470d5570a713bd45dd40288765bd_52.png)

![](img/7b25470d5570a713bd45dd40288765bd_53.png)

![](img/7b25470d5570a713bd45dd40288765bd_54.png)

# 遍历列表并访问每个实例的变量
for package in packages:
    print(f"Package {package.number}: {package.sender} to {package.recipient}, {package.weight}kg")
```

![](img/7b25470d5570a713bd45dd40288765bd_55.png)

![](img/7b25470d5570a713bd45dd40288765bd_56.png)

![](img/7b25470d5570a713bd45dd40288765bd_57.png)

![](img/7b25470d5570a713bd45dd40288765bd_58.png)

![](img/7b25470d5570a713bd45dd40288765bd_59.png)

运行这段代码，你将看到每个包裹的详细信息被清晰地打印出来。

---

## 实例变量的核心作用

![](img/7b25470d5570a713bd45dd40288765bd_61.png)

![](img/7b25470d5570a713bd45dd40288765bd_62.png)

![](img/7b25470d5570a713bd45dd40288765bd_63.png)

![](img/7b25470d5570a713bd45dd40288765bd_64.png)

![](img/7b25470d5570a713bd45dd40288765bd_65.png)

以下是实例变量的几个关键点：

![](img/7b25470d5570a713bd45dd40288765bd_66.png)

![](img/7b25470d5570a713bd45dd40288765bd_67.png)

![](img/7b25470d5570a713bd45dd40288765bd_68.png)

*   **独立性**：每个实例的变量值都是独立的。更改 `package1.sender` 不会影响 `package2.sender`。
*   **封装数据**：实例变量将数据（属性）和行为（未来会学的方法）捆绑在单个对象内，这是面向对象编程的基石。
*   **通过 `self` 定义**：在类的方法内部，必须通过 `self.变量名` 来定义和访问实例变量，以明确它是属于当前实例的。

![](img/7b25470d5570a713bd45dd40288765bd_70.png)

![](img/7b25470d5570a713bd45dd40288765bd_71.png)

![](img/7b25470d5570a713bd45dd40288765bd_72.png)

---

![](img/7b25470d5570a713bd45dd40288765bd_73.png)

## 总结

本节课中我们一起学习了**实例变量**。我们了解到：

![](img/7b25470d5570a713bd45dd40288765bd_75.png)

![](img/7b25470d5570a713bd45dd40288765bd_76.png)

1.  实例变量是定义在类的方法内部（尤其是 `__init__` 中）、以 `self.` 开头的变量。
2.  它们用于存储每个类实例独有的数据。
3.  我们可以通过 `实例.变量名` 的方式在类外部访问这些变量。
4.  实例变量实现了数据的封装，是构建复杂、有状态对象的基础。

![](img/7b25470d5570a713bd45dd40288765bd_77.png)

![](img/7b25470d5570a713bd45dd40288765bd_78.png)

![](img/7b25470d5570a713bd45dd40288765bd_80.png)

通过使用实例变量，我们能够创建出具有丰富属性和行为的自定义数据类型，这是用Python进行有效编程的关键一步。