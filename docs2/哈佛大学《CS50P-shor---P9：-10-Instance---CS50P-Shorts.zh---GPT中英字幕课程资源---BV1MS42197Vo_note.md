# 哈佛大学《CS50P Python编程入门》短课程 - P9：实例方法 🧩

![](img/2749873fe240ad6c6aff3cb9929078a9_0.png)

在本节课中，我们将要学习 Python 类中的一个核心概念：**实例方法**。我们将了解如何为类定义方法，这些方法可以操作类的实例，并封装与对象相关的功能。

![](img/2749873fe240ad6c6aff3cb9929078a9_2.png)

---

![](img/2749873fe240ad6c6aff3cb9929078a9_3.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_4.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_5.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_6.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_7.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_8.png)

在之前的课程中，我们学习了如何定义类和实例变量，即如何为对象创建模板，以及如何实例化这些模板的个体来编码和访问它们的各种属性。

![](img/2749873fe240ad6c6aff3cb9929078a9_9.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_10.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_11.png)

例如，我们有一个名为 `Package` 的类，它封装了关于包裹的通用信息。我们定义每个包裹都有编号、发件人、收件人和重量等属性。

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight
```

![](img/2749873fe240ad6c6aff3cb9929078a9_13.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_14.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_15.png)

在第11行和第12行，我们创建了这些类的实例。第一个包裹的编号是1，发件人是Alice，收件人是Bob，重量是10公斤。在第14行，我们编写了访问这些实例变量的代码，以更美观的格式打印包裹信息。

![](img/2749873fe240ad6c6aff3cb9929078a9_16.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_17.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_18.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_19.png)

运行此代码，我们可以看到成功打印了两个包裹的信息。这展示了如何以更有组织的方式封装和组合信息。

![](img/2749873fe240ad6c6aff3cb9929078a9_21.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_22.png)

---

![](img/2749873fe240ad6c6aff3cb9929078a9_23.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_24.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_25.png)

然而，类的用途不仅限于封装信息，还可以封装**功能**，这些功能对于该类的所有实例都应该是通用的。

![](img/2749873fe240ad6c6aff3cb9929078a9_27.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_28.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_29.png)

我们可以通过定义**实例方法**来实现这一点。实例方法是可以在此特定类的任何实例上运行的方法。

![](img/2749873fe240ad6c6aff3cb9929078a9_30.png)

这里的“方法”指的是一种特殊的函数，它是类的一部分。我们将介绍一个非常实用的特殊方法：`__str__` 方法（读作“dunder str”）。

![](img/2749873fe240ad6c6aff3cb9929078a9_32.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_33.png)

与 `__init__` 类似，`__str__` 是一个特殊的实例方法。当尝试打印某个类的实例时，Python 会自动调用这个方法。

![](img/2749873fe240ad6c6aff3cb9929078a9_34.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_35.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_36.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_37.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_38.png)

目前，在第15行，我们有一长串打印包裹信息的代码。如果能简单地使用 `print(package)` 并得到相同的格式化输出，那将会方便得多。

但如果我们直接运行 `print(package)`，输出会很不美观。我们可以通过添加 `__str__` 实例方法来改善打印任何 `Package` 类实例时的输出效果。

![](img/2749873fe240ad6c6aff3cb9929078a9_40.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_41.png)

---

![](img/2749873fe240ad6c6aff3cb9929078a9_42.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_43.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_44.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_45.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_46.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_47.png)

让我们回到类定义中，添加这个新的实例方法。

![](img/2749873fe240ad6c6aff3cb9929078a9_49.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_50.png)

我们只需在类中定义一个新函数。由于这是一个 Python 赋予特殊功能的方法，我们使用双下划线 `__str__` 来命名它。

![](img/2749873fe240ad6c6aff3cb9929078a9_52.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_53.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_55.png)

按照约定，`__str__` 方法将类实例本身作为第一个参数，我们通常称之为 `self`。

![](img/2749873fe240ad6c6aff3cb9929078a9_57.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_59.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_61.png)

在 `__str__` 方法内部，我们可以返回一个字符串。每当我们对 `Package` 的实例调用 `print` 时，就会打印这个字符串。

首先，我们可以做一个简单的测试，让方法返回 `"This is a package"`。这样，每次打印包裹时都会看到这句话。

![](img/2749873fe240ad6c6aff3cb9929078a9_63.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_64.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_65.png)

但理想情况下，我们应该显示关于当前实例的具体信息。为此，我们可以在方法内部访问实例变量，并使用 f-string 返回格式化的字符串，就像之前在第14行做的那样。

![](img/2749873fe240ad6c6aff3cb9929078a9_66.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_67.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_68.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_69.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_70.png)

我们可以返回类似 `f"Package {self.number}: {self.sender} to {self.recipient}, {self.weight}kg"` 的字符串。

![](img/2749873fe240ad6c6aff3cb9929078a9_72.png)

现在，当我们再次运行程序并直接打印包裹实例时，就会看到格式美观的详细信息。我们将相同的 f-string 逻辑封装在了 `Package` 类的 `__str__` 实例方法中。

![](img/2749873fe240ad6c6aff3cb9929078a9_73.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_74.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_75.png)

---

实例方法还能用来做什么？我们可能希望为“包裹”这个概念附加一些核心功能。

![](img/2749873fe240ad6c6aff3cb9929078a9_77.png)

例如，我们可能希望包裹能够计算自己的运费。我们可以定义另一个名为 `calculate_cost` 的实例方法。

![](img/2749873fe240ad6c6aff3cb9929078a9_78.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_79.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_80.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_81.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_82.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_83.png)

这个方法的默认第一个参数同样是实例本身 `self`。此外，我们还可以为它添加其他参数，比如每公斤的运费单价。

![](img/2749873fe240ad6c6aff3cb9929078a9_84.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_86.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_87.png)

在方法体内，我们可以实现计算逻辑：用包裹的重量（`self.weight`）乘以每公斤单价，得到总运费。

![](img/2749873fe240ad6c6aff3cb9929078a9_88.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_90.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_91.png)

定义好方法后，我们就可以使用它了。在循环遍历包裹列表时，可以对每个包裹实例调用 `package.calculate_cost(cost_per_kg)`，并传入单价（例如2美元/公斤）。

![](img/2749873fe240ad6c6aff3cb9929078a9_93.png)

最后，我们可以在打印信息时，将计算出的运费也一并输出，使信息更加完整。

![](img/2749873fe240ad6c6aff3cb9929078a9_94.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_95.png)

---

以下是本节课的完整代码示例，展示了类的定义、`__str__` 方法和自定义实例方法的使用：

![](img/2749873fe240ad6c6aff3cb9929078a9_97.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_98.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_99.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_100.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_101.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_102.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight

    def __str__(self):
        return f"Package {self.number}: {self.sender} to {self.recipient}, {self.weight}kg"

    def calculate_cost(self, cost_per_kg):
        return self.weight * cost_per_kg


![](img/2749873fe240ad6c6aff3cb9929078a9_103.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_105.png)

# 创建实例
package1 = Package(1, "Alice", "Bob", 10)
package2 = Package(2, "Bob", "Charlie", 5)

packages = [package1, package2]

# 使用实例方法
for package in packages:
    cost = package.calculate_cost(2)  # 假设运费为2美元/公斤
    print(f"{package} costs ${cost}")
```

![](img/2749873fe240ad6c6aff3cb9929078a9_107.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_108.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_109.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_110.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_111.png)

---

![](img/2749873fe240ad6c6aff3cb9929078a9_113.png)

本节课中我们一起学习了：
1.  **实例方法的概念**：它是定义在类内部的函数，用于操作类的实例。
2.  **特殊方法 `__str__`**：用于定义打印类实例时的字符串表示形式，使输出更友好。
3.  **自定义实例方法**：如 `calculate_cost`，用于封装与对象相关的特定功能。
4.  **方法的调用**：通过实例名加点号 `.` 再加方法名来调用，例如 `package.calculate_cost(2)`。

通过使用实例方法，我们能够将数据和对数据的操作捆绑在一起，使代码更加模块化、易读和易维护。这是面向对象编程的核心优势之一。