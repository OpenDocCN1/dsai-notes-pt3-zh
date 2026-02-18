# 44：继承的实现与配置 🏥➡️👨‍⚕️👩‍⚕️

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_0.png)

在本节课中，我们将学习面向对象编程中一个核心概念——继承。我们将通过创建一个医院员工系统的例子，来演示如何构建父类与子类，并理解它们之间的关系和工作方式。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_2.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_3.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_4.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_6.png)

## 概述：什么是继承？

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_8.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_10.png)

继承允许我们定义一个类（子类）来继承另一个类（父类）的属性和方法。这有助于代码重用，并能在子类中创建更具体的行为。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_11.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_13.png)

上一节我们介绍了类的基本概念，本节中我们来看看如何通过继承来构建更复杂的类层次结构。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_15.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_16.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_18.png)

## 创建父类：医院员工

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_20.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_22.png)

首先，我们需要创建一个基础的父类 `HospitalEmployee`。这个类将包含所有医院员工共有的基本属性。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_24.png)

```python
class HospitalEmployee:
    def __init__(self, emp_name, emp_number, hourly_pay, hours_worked):
        self.employee_name = emp_name
        self.employee_number = emp_number
        self.hourly_pay = hourly_pay
        self.hours_worked = hours_worked
        self.pay = 0  # 设置总薪酬的基线
```

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_26.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_27.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_28.png)

在构造函数 `__init__` 中，我们初始化了四个属性：员工姓名、工号、时薪和工作小时数。同时，我们将总薪酬 `pay` 初始化为0。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_29.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_31.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_33.png)

## 为父类添加方法

为了使类更实用，我们需要添加一些方法来设置和获取属性值，以及计算和显示薪酬。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_35.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_36.png)

以下是设置器和获取器（Setters and Getters）的示例：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_37.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_38.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_39.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_41.png)

```python
    def set_employee_name(self, e_name):
        self.employee_name = e_name

    def get_employee_name(self):
        return self.employee_name

    def set_employee_number(self, e_number):
        self.employee_number = e_number

    def get_employee_number(self):
        return self.employee_number

    def set_hourly_pay(self, h_pay):
        self.hourly_pay = h_pay

    def get_hourly_pay(self):
        return self.hourly_pay

    def set_hours_worked(self, h_worked):
        self.hours_worked = h_worked

    def get_hours_worked(self):
        return self.hours_worked
```

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_43.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_45.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_47.png)

接下来，我们添加计算薪酬和显示信息的方法：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_49.png)

```python
    def calculate_pay(self):
        self.pay = self.hourly_pay * self.hours_worked
        return self.pay

    def display(self):
        self.calculate_pay()
        print(f"员工姓名: {self.get_employee_name()}")
        print(f"员工工号: {self.get_employee_number()}")
        print(f"时薪: ${self.get_hourly_pay():.2f}")
        print(f"工作小时数: {self.get_hours_worked()}")
        print(f"总薪酬: ${self.pay:.2f}")
```

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_51.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_52.png)

在 `display` 方法中，我们首先调用 `calculate_pay` 来计算总薪酬，然后使用格式化字符串打印出所有员工信息。`:.2f` 用于将数字格式化为带有两位小数的货币形式。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_54.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_55.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_56.png)

## 创建子类：医生

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_58.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_60.png)

现在，我们来创建第一个子类 `Doctor`。医生是一种特殊的医院员工，拥有自己的独特属性，例如专业领域。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_62.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_64.png)

定义子类时，需要在类名后的括号中指定其父类：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_66.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_67.png)

```python
class Doctor(HospitalEmployee):
    def __init__(self, specialty, emp_name, emp_number, hourly_pay, hours_worked):
        self.specialty = specialty  # 医生特有的属性
        super().__init__(emp_name, emp_number, hourly_pay, hours_worked)
```

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_69.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_71.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_73.png)

在 `Doctor` 类的构造函数中：
1.  我们首先初始化子类特有的属性 `specialty`。
2.  然后使用 `super().__init__(...)` 调用父类 `HospitalEmployee` 的构造函数，来初始化共有的属性（姓名、工号等）。`super()` 函数返回一个代表父类的临时对象，允许我们调用父类的方法。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_75.png)

## 创建子类：护士

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_76.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_77.png)

同样地，我们可以创建 `Nurse` 子类。其结构与 `Doctor` 类类似。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_79.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_80.png)

```python
class Nurse(HospitalEmployee):
    def __init__(self, specialty, emp_name, emp_number, hourly_pay, hours_worked):
        self.specialty = specialty
        super().__init__(emp_name, emp_number, hourly_pay, hours_worked)
```

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_82.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_83.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_85.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_87.png)

通过继承，`Nurse` 类自动拥有了父类 `HospitalEmployee` 的所有属性和方法，同时添加了自己的 `specialty` 属性。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_89.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_91.png)

## 方法的覆盖与扩展

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_93.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_95.png)

子类可以拥有与父类同名的方法。当调用该方法时，Python会优先使用子类中的版本。这称为方法覆盖。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_97.png)

例如，我们可以在 `Nurse` 类中创建一个新的 `display` 方法，它既显示父类的信息，也显示护士特有的专业信息：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_99.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_101.png)

```python
class Nurse(HospitalEmployee):
    # ... __init__ 方法同上 ...

    def display(self):
        super().display()  # 调用父类的display方法
        print(f"专业领域: {self.specialty}")
```

在这个新的 `display` 方法中：
1.  `super().display()` 调用了父类 `HospitalEmployee` 的 `display` 方法，打印出基础信息。
2.  然后额外打印了 `specialty` 属性。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_103.png)

我们同样更新 `Doctor` 类的 `display` 方法：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_105.png)

```python
class Doctor(HospitalEmployee):
    # ... __init__ 方法同上 ...

    def display(self):
        super().display()
        print(f"专业领域: {self.specialty}")
```

## 使用继承的类

现在，让我们创建对象并看看继承是如何工作的。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_107.png)

首先，创建一个护士对象：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_109.png)

```python
emp1 = Nurse("创伤科护士", "Tina Baldwin", "1223212", 65.54, 40)
emp1.display()
```

运行这段代码，输出将包含从父类继承的基本信息以及子类添加的专业领域。

接着，创建一个医生对象：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_111.png)

```python
emp2 = Doctor("产科与分娩科医生", "Michael Smith", "12345678", 89.54, 40)
emp2.display()
```

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_113.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_115.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_117.png)

## 关于 `super()` 的注意事项

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_119.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_120.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_122.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_124.png)

*   在单继承（一个子类只有一个父类）中，使用 `super()` 是调用父类方法的推荐方式，它使代码更清晰、更易于维护。
*   在处理多继承（一个子类有多个父类）时，为了明确指定调用哪个父类的方法，有时可能需要显式地使用父类名进行调用，例如 `HospitalEmployee.display(self)`。但在入门阶段，我们主要关注单继承。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_125.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_127.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_129.png)

## 总结

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_131.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_133.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_135.png)

本节课中我们一起学习了面向对象编程中继承的核心机制。我们了解到：

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_136.png)

1.  **继承** 允许子类获取并扩展父类的属性和方法。
2.  定义子类时，语法为 `class ChildClass(ParentClass):`。
3.  在子类构造函数中，通常先初始化子类特有的属性，然后使用 `super().__init__(...)` 调用父类构造函数来初始化共有属性。
4.  子类可以 **覆盖** 父类的方法以提供特定实现，也可以通过 `super()` 调用父类方法并在其基础上进行 **扩展**。
5.  继承促进了代码的 **重用性** 和 **组织性**，是构建复杂程序的重要工具。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_138.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_139.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_141.png)

通过构建医院员工、医生和护士的类层次结构，我们实践了如何利用继承来优雅地建模现实世界中的“是一个（is-a）”关系。