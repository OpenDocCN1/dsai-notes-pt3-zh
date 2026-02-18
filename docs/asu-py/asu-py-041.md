# 41：Python面向对象与类的应用（第二部分）🚗

![](img/dafd4a623b7cae339ab51b1c7c69c71d_0.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_2.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_4.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_6.png)

在本节课中，我们将深入学习Python中类的方法结构、对象的创建过程、以及属性的不同类型。我们将通过具体的代码示例，详细解析构造方法、访问器方法（getter/setter）的工作原理，并探讨如何通过变通方式实现方法重载。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_8.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_9.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_11.png)

---

![](img/dafd4a623b7cae339ab51b1c7c69c71d_13.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_14.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_16.png)

## 方法的结构解析 🔍

![](img/dafd4a623b7cae339ab51b1c7c69c71d_18.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_20.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_22.png)

上一节我们介绍了类的基本概念，本节中我们来看看如何定义一个类的方法。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_24.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_26.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_28.png)

方法的结构由几个关键部分组成。以下是定义一个方法的通用格式：

![](img/dafd4a623b7cae339ab51b1c7c69c71d_30.png)

```python
def method_name(self, parameter1, parameter2):
    # 方法体
    return result
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_32.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_33.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_34.png)

以下是方法各组成部分的详细说明：

![](img/dafd4a623b7cae339ab51b1c7c69c71d_36.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_37.png)

*   **`def` 关键字**： 用于定义方法。
*   **方法名**： 方法的名称，例如 `multiply`。
*   **参数 `self`**： 代表对象自身的引用，是类方法的第一个参数。
*   **其他参数**： 方法可以接收的额外变量，例如 `x` 和 `y`。
*   **方法体**： 方法内部执行的代码块。
*   **`return` 语句**： 将结果返回给调用该方法的代码。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_38.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_39.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_40.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_42.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_44.png)

---

![](img/dafd4a623b7cae339ab51b1c7c69c71d_46.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_48.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_50.png)

## 对象的创建与内存模型 💾

![](img/dafd4a623b7cae339ab51b1c7c69c71d_52.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_53.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_55.png)

理解了方法结构后，我们来看看如何创建对象以及对象在内存中是如何存储的。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_57.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_59.png)

创建对象时，我们首先需要为其指定一个变量名。例如：

![](img/dafd4a623b7cae339ab51b1c7c69c71d_61.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_62.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_64.png)

```python
ford = Car(2021, 130)
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_65.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_67.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_69.png)

在这个例子中，`ford` 是变量名，`Car(2021, 130)` 会调用类的构造方法来初始化一个对象。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_70.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_72.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_73.png)

对象在内存中的处理方式与普通变量不同。普通变量（如 `name = “Sam”`）直接指向存储值的内存地址。而对象可能包含多个数据片段，这些数据被存储在一个连续的内存块中。对象变量（如 `ford`）存储的是这个内存块起始位置的地址。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_75.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_77.png)

---

![](img/dafd4a623b7cae339ab51b1c7c69c71d_78.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_80.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_82.png)

## 构造方法与访问器 🛠️

![](img/dafd4a623b7cae339ab51b1c7c69c71d_84.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_85.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_87.png)

让我们通过一个 `Car` 类的具体例子，深入理解构造方法和访问器。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_89.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_91.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_92.png)

首先，我们定义一个 `Car` 类，并使用 `__init__` 方法作为构造方法。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_93.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_95.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_97.png)

```python
class Car:
    def __init__(self, year, speed):
        self.year = year
        self.speed = speed
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_99.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_101.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_103.png)

*   **`__init__` 方法**： 这是一个特殊方法，代表类的构造函数。它像一张蓝图，规定了对象如何被初始化。
*   **参数 `self`**： 指代正在创建的对象本身。
*   **实例变量赋值**： `self.year = year` 将传入的 `year` 参数值赋给对象的 `year` 属性。`self.speed = speed` 同理。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_105.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_106.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_107.png)

为了能够灵活地修改或获取对象的属性，我们通常需要定义访问器方法。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_109.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_111.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_113.png)

以下是设置和获取速度的访问器方法：

![](img/dafd4a623b7cae339ab51b1c7c69c71d_115.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_117.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_119.png)

```python
    def get_speed(self):
        return self.speed

    def set_speed(self, new_speed):
        self.speed = new_speed
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_121.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_122.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_124.png)

*   **Getter（获取器）**： 如 `get_speed`，用于返回属性的值。
*   **Setter（设置器）**： 如 `set_speed`，用于修改属性的值。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_126.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_128.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_130.png)

现在，我们可以创建对象并操作其属性：

```python
ford = Car(2021, 130) # 调用 __init__，创建对象并初始化
chevy = Car(2019, 110)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_132.png)

print(ford.get_speed()) # 输出: 130
print(chevy.get_speed()) # 输出: 110

![](img/dafd4a623b7cae339ab51b1c7c69c71d_133.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_134.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_135.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_136.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_137.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_138.png)

ford.set_speed(120) # 修改 ford 的速度
print(ford.get_speed()) # 输出: 120
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_140.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_141.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_143.png)

当执行 `ford = Car(2021, 130)` 时，Python 会找到 `Car` 类的 `__init__` 方法，并传入参数来创建和初始化 `ford` 对象。调用 `ford.set_speed(120)` 时，方法会接收 `ford` 对象和新的速度值，并完成重新赋值。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_145.png)

---

![](img/dafd4a623b7cae339ab51b1c7c69c71d_146.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_147.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_148.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_150.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_152.png)

## 实例属性与类属性 📊

![](img/dafd4a623b7cae339ab51b1c7c69c71d_154.png)

对象存储的数据称为属性。属性主要分为两种类型：

![](img/dafd4a623b7cae339ab51b1c7c69c71d_156.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_157.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_158.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_159.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_161.png)

*   **实例属性**： 由类的每个实例对象单独拥有。每个对象的实例属性值可以不同。我们之前定义的 `year` 和 `speed` 就是实例属性。
*   **类属性**： 由类本身拥有，所有实例对象共享同一个值。这类似于其他编程语言中的静态变量。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_163.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_165.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_166.png)

两者的区别在于定义位置：实例属性通常在 `__init__` 方法内通过 `self.attribute_name` 定义；而类属性在类内部、方法外部直接定义。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_168.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_169.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_171.png)

在之前的 `Car` 类中，我们没有定义类属性。下面是一个包含类属性的 `BankAccount` 类示例：

![](img/dafd4a623b7cae339ab51b1c7c69c71d_173.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_174.png)

```python
class BankAccount:
    # 类属性（此示例中未实际使用，仅为展示定义位置）
    bank_name = “Python Bank”

    def __init__(self, *args):
        # 实例属性在 __init__ 中初始化
        ...
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_176.png)

---

![](img/dafd4a623b7cae339ab51b1c7c69c71d_177.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_178.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_179.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_180.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_182.png)

## 实现方法重载的变通方案 🔄

![](img/dafd4a623b7cae339ab51b1c7c69c71d_184.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_186.png)

有些编程语言允许方法重载，即定义多个同名但参数不同的方法。Python 本身不直接支持这种重载，但我们可以使用变通方案。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_188.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_189.png)

假设我们想为 `BankAccount` 类提供两种构造方式：一种使用默认值，另一种接收具体参数。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_191.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_193.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_194.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_196.png)

一种常见的变通方法是使用 `*args`（可变参数列表）在单个 `__init__` 方法中处理不同数量的参数。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_198.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_200.png)

```python
class BankAccount:
    def __init__(self, *args):
        if len(args) < 3: # 如果参数少于3个，使用默认值
            self.name = “Unknown”
            self.account_number = 1234
            self.balance = 0.0
        else: # 否则，使用传入的参数
            self.name = args[0]
            self.account_number = args[1]
            self.balance = args[2]

    # Getter 和 Setter 方法
    def get_balance(self):
        return self.balance

    def deposit(self, amount):
        self.balance += amount # 存款

    def withdraw(self, amount):
        self.balance -= amount # 取款

    def __str__(self):
        return f“Name: {self.name}, Acc#: {self.account_number}, Balance: ${self.balance}”
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_202.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_204.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_205.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_207.png)

通过检查 `args` 的长度，我们可以决定是使用默认值还是使用用户提供的值来初始化对象。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_209.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_211.png)

```python
# 使用默认值创建账户
account1 = BankAccount()
print(account1) # 输出: Name: Unknown, Acc#: 1234, Balance: $0.0

![](img/dafd4a623b7cae339ab51b1c7c69c71d_213.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_214.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_215.png)

# 使用具体参数创建账户
account2 = BankAccount(“Tim”, 5678, 1000.0)
print(account2) # 输出: Name: Tim, Acc#: 5678, Balance: $1000.0

![](img/dafd4a623b7cae339ab51b1c7c69c71d_217.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_218.png)

account2.deposit(500)
print(account2.get_balance()) # 输出: 1500.0
```

![](img/dafd4a623b7cae339ab51b1c7c69c71d_220.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_221.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_223.png)

---

![](img/dafd4a623b7cae339ab51b1c7c69c71d_225.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_227.png)

## 总结 🎯

![](img/dafd4a623b7cae339ab51b1c7c69c71d_229.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_231.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_233.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_234.png)

本节课中我们一起学习了：
1.  **方法的结构**，包括 `def` 关键字、`self` 参数和返回值。
2.  **对象的创建与内存模型**，理解了对象变量存储的是内存地址引用。
3.  **构造方法 `__init__`** 的作用，以及如何使用 **Getter 和 Setter** 方法来访问和修改对象属性。
4.  **实例属性与类属性**的区别，实例属性属于对象，类属性由所有对象共享。
5.  通过使用 ***args** 可变参数，实现了类似方法重载的功能，以灵活处理不同初始化场景。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_236.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_237.png)

这些知识是构建复杂、模块化Python程序的基础。接下来，我们将通过一个创建“员工”类的实际演示来巩固这些概念。