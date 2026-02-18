# 42：Python面向对象与类的应用（第三部分） 🐍

![](img/b1c904e774b84edc564f31676f4d3892_0.png)

![](img/b1c904e774b84edc564f31676f4d3892_2.png)

![](img/b1c904e774b84edc564f31676f4d3892_4.png)

![](img/b1c904e774b84edc564f31676f4d3892_6.png)

![](img/b1c904e774b84edc564f31676f4d3892_7.png)

![](img/b1c904e774b84edc564f31676f4d3892_9.png)

![](img/b1c904e774b84edc564f31676f4d3892_11.png)

![](img/b1c904e774b84edc564f31676f4d3892_13.png)

在本节课中，我们将学习如何创建一个完整的Python类，包括构造函数、方法以及如何通过设置器（setter）和获取器（getter）来修改和访问对象的属性。我们还将探讨Python中如何处理构造函数重载的问题。

![](img/b1c904e774b84edc564f31676f4d3892_15.png)

![](img/b1c904e774b84edc564f31676f4d3892_17.png)

---

![](img/b1c904e774b84edc564f31676f4d3892_19.png)

![](img/b1c904e774b84edc564f31676f4d3892_20.png)

![](img/b1c904e774b84edc564f31676f4d3892_21.png)

![](img/b1c904e774b84edc564f31676f4d3892_22.png)

![](img/b1c904e774b84edc564f31676f4d3892_24.png)

## 创建类与构造函数

![](img/b1c904e774b84edc564f31676f4d3892_26.png)

![](img/b1c904e774b84edc564f31676f4d3892_27.png)

![](img/b1c904e774b84edc564f31676f4d3892_29.png)

![](img/b1c904e774b84edc564f31676f4d3892_31.png)

![](img/b1c904e774b84edc564f31676f4d3892_33.png)

![](img/b1c904e774b84edc564f31676f4d3892_35.png)

首先，我们创建一个名为 `Employee` 的类。我们将定义其构造函数，用于初始化员工对象的属性。

![](img/b1c904e774b84edc564f31676f4d3892_36.png)

![](img/b1c904e774b84edc564f31676f4d3892_38.png)

![](img/b1c904e774b84edc564f31676f4d3892_40.png)

![](img/b1c904e774b84edc564f31676f4d3892_41.png)

```python
class Employee:
    def __init__(self, *args):
        if len(args) < 4:
            self.ID = 1000
            self.first_name = "unknown"
            self.last_name = "unknown"
            self.salary = 0
        else:
            self.ID = args[0]
            self.first_name = args[1]
            self.last_name = args[2]
            self.salary = args[3]
```

![](img/b1c904e774b84edc564f31676f4d3892_43.png)

![](img/b1c904e774b84edc564f31676f4d3892_45.png)

![](img/b1c904e774b84edc564f31676f4d3892_47.png)

![](img/b1c904e774b84edc564f31676f4d3892_49.png)

![](img/b1c904e774b84edc564f31676f4d3892_51.png)

在上面的代码中，我们使用 `*args` 来接收可变数量的参数。通过检查参数的长度，我们可以决定是使用默认值还是使用传入的参数来初始化对象的属性。

![](img/b1c904e774b84edc564f31676f4d3892_53.png)

![](img/b1c904e774b84edc564f31676f4d3892_55.png)

![](img/b1c904e774b84edc564f31676f4d3892_57.png)

![](img/b1c904e774b84edc564f31676f4d3892_59.png)

![](img/b1c904e774b84edc564f31676f4d3892_60.png)

![](img/b1c904e774b84edc564f31676f4d3892_62.png)

![](img/b1c904e774b84edc564f31676f4d3892_64.png)

---

![](img/b1c904e774b84edc564f31676f4d3892_66.png)

![](img/b1c904e774b84edc564f31676f4d3892_68.png)

![](img/b1c904e774b84edc564f31676f4d3892_70.png)

![](img/b1c904e774b84edc564f31676f4d3892_72.png)

![](img/b1c904e774b84edc564f31676f4d3892_74.png)

![](img/b1c904e774b84edc564f31676f4d3892_76.png)

## 显示对象信息的方法

![](img/b1c904e774b84edc564f31676f4d3892_77.png)

![](img/b1c904e774b84edc564f31676f4d3892_79.png)

![](img/b1c904e774b84edc564f31676f4d3892_81.png)

![](img/b1c904e774b84edc564f31676f4d3892_82.png)

![](img/b1c904e774b84edc564f31676f4d3892_84.png)

![](img/b1c904e774b84edc564f31676f4d3892_86.png)

![](img/b1c904e774b84edc564f31676f4d3892_87.png)

接下来，我们创建一个 `display` 方法，用于打印员工对象的所有信息。为了使输出更清晰，我们使用 `\n` 在每个属性后换行。

![](img/b1c904e774b84edc564f31676f4d3892_89.png)

![](img/b1c904e774b84edc564f31676f4d3892_91.png)

![](img/b1c904e774b84edc564f31676f4d3892_93.png)

![](img/b1c904e774b84edc564f31676f4d3892_94.png)

![](img/b1c904e774b84edc564f31676f4d3892_96.png)

```python
    def display(self):
        print("Employee ID:", self.ID, "\nFirst Name:", self.first_name, "\nLast Name:", self.last_name, "\nSalary:", self.salary)
```

![](img/b1c904e774b84edc564f31676f4d3892_98.png)

![](img/b1c904e774b84edc564f31676f4d3892_99.png)

![](img/b1c904e774b84edc564f31676f4d3892_101.png)

![](img/b1c904e774b84edc564f31676f4d3892_102.png)

`\n` 是一个转义字符，表示换行。使用它可以让每个属性单独显示在一行，使输出更易读。

![](img/b1c904e774b84edc564f31676f4d3892_104.png)

![](img/b1c904e774b84edc564f31676f4d3892_105.png)

![](img/b1c904e774b84edc564f31676f4d3892_107.png)

![](img/b1c904e774b84edc564f31676f4d3892_108.png)

![](img/b1c904e774b84edc564f31676f4d3892_109.png)

![](img/b1c904e774b84edc564f31676f4d3892_110.png)

---

![](img/b1c904e774b84edc564f31676f4d3892_112.png)

![](img/b1c904e774b84edc564f31676f4d3892_113.png)

![](img/b1c904e774b84edc564f31676f4d3892_115.png)

![](img/b1c904e774b84edc564f31676f4d3892_117.png)

![](img/b1c904e774b84edc564f31676f4d3892_119.png)

## 创建对象并测试

![](img/b1c904e774b84edc564f31676f4d3892_121.png)

![](img/b1c904e774b84edc564f31676f4d3892_123.png)

![](img/b1c904e774b84edc564f31676f4d3892_125.png)

![](img/b1c904e774b84edc564f31676f4d3892_127.png)

![](img/b1c904e774b84edc564f31676f4d3892_129.png)

现在，我们创建两个 `Employee` 对象：一个使用默认参数，另一个使用自定义参数。

![](img/b1c904e774b84edc564f31676f4d3892_131.png)

![](img/b1c904e774b84edc564f31676f4d3892_132.png)

![](img/b1c904e774b84edc564f31676f4d3892_134.png)

![](img/b1c904e774b84edc564f31676f4d3892_135.png)

![](img/b1c904e774b84edc564f31676f4d3892_137.png)

```python
emp1 = Employee()
emp2 = Employee(1234, "Bob", "Smith", 36000)
```

![](img/b1c904e774b84edc564f31676f4d3892_139.png)

![](img/b1c904e774b84edc564f31676f4d3892_140.png)

![](img/b1c904e774b84edc564f31676f4d3892_142.png)

![](img/b1c904e774b84edc564f31676f4d3892_144.png)

![](img/b1c904e774b84edc564f31676f4d3892_146.png)

然后，我们调用 `display` 方法来查看这两个对象的信息。

![](img/b1c904e774b84edc564f31676f4d3892_148.png)

![](img/b1c904e774b84edc564f31676f4d3892_150.png)

![](img/b1c904e774b84edc564f31676f4d3892_151.png)

![](img/b1c904e774b84edc564f31676f4d3892_153.png)

```python
emp1.display()
print()  # 用于分隔输出
emp2.display()
```

![](img/b1c904e774b84edc564f31676f4d3892_155.png)

![](img/b1c904e774b84edc564f31676f4d3892_157.png)

![](img/b1c904e774b84edc564f31676f4d3892_159.png)

![](img/b1c904e774b84edc564f31676f4d3892_161.png)

运行上述代码，你将看到第一个员工的信息是默认值，而第二个员工的信息是我们传入的自定义值。

![](img/b1c904e774b84edc564f31676f4d3892_163.png)

![](img/b1c904e774b84edc564f31676f4d3892_165.png)

![](img/b1c904e774b84edc564f31676f4d3892_167.png)

![](img/b1c904e774b84edc564f31676f4d3892_169.png)

![](img/b1c904e774b84edc564f31676f4d3892_171.png)

![](img/b1c904e774b84edc564f31676f4d3892_173.png)

---

![](img/b1c904e774b84edc564f31676f4d3892_175.png)

![](img/b1c904e774b84edc564f31676f4d3892_177.png)

![](img/b1c904e774b84edc564f31676f4d3892_178.png)

![](img/b1c904e774b84edc564f31676f4d3892_180.png)

![](img/b1c904e774b84edc564f31676f4d3892_181.png)

## 设置器与获取器

![](img/b1c904e774b84edc564f31676f4d3892_183.png)

![](img/b1c904e774b84edc564f31676f4d3892_184.png)

![](img/b1c904e774b84edc564f31676f4d3892_186.png)

![](img/b1c904e774b84edc564f31676f4d3892_188.png)

![](img/b1c904e774b84edc564f31676f4d3892_190.png)

为了能够修改和访问对象的属性，我们创建设置器（setter）和获取器（getter）方法。

![](img/b1c904e774b84edc564f31676f4d3892_192.png)

![](img/b1c904e774b84edc564f31676f4d3892_194.png)

![](img/b1c904e774b84edc564f31676f4d3892_196.png)

![](img/b1c904e774b84edc564f31676f4d3892_198.png)

![](img/b1c904e774b84edc564f31676f4d3892_200.png)

以下是获取器方法的示例：

![](img/b1c904e774b84edc564f31676f4d3892_202.png)

![](img/b1c904e774b84edc564f31676f4d3892_203.png)

![](img/b1c904e774b84edc564f31676f4d3892_204.png)

![](img/b1c904e774b84edc564f31676f4d3892_206.png)

```python
    def get_ID(self):
        return self.ID

    def get_first_name(self):
        return self.first_name

    def get_last_name(self):
        return self.last_name

    def get_salary(self):
        return self.salary
```

![](img/b1c904e774b84edc564f31676f4d3892_208.png)

![](img/b1c904e774b84edc564f31676f4d3892_209.png)

![](img/b1c904e774b84edc564f31676f4d3892_211.png)

![](img/b1c904e774b84edc564f31676f4d3892_212.png)

![](img/b1c904e774b84edc564f31676f4d3892_214.png)

以下是设置器方法的示例：

![](img/b1c904e774b84edc564f31676f4d3892_216.png)

![](img/b1c904e774b84edc564f31676f4d3892_218.png)

![](img/b1c904e774b84edc564f31676f4d3892_220.png)

![](img/b1c904e774b84edc564f31676f4d3892_222.png)

![](img/b1c904e774b84edc564f31676f4d3892_224.png)

```python
    def set_ID(self, ID):
        self.ID = ID

    def set_first_name(self, first_name):
        self.first_name = first_name

    def set_last_name(self, last_name):
        self.last_name = last_name

    def set_salary(self, salary):
        self.salary = salary
```

![](img/b1c904e774b84edc564f31676f4d3892_225.png)

![](img/b1c904e774b84edc564f31676f4d3892_227.png)

![](img/b1c904e774b84edc564f31676f4d3892_229.png)

![](img/b1c904e774b84edc564f31676f4d3892_231.png)

![](img/b1c904e774b84edc564f31676f4d3892_233.png)

![](img/b1c904e774b84edc564f31676f4d3892_235.png)

![](img/b1c904e774b84edc564f31676f4d3892_237.png)

通过这些方法，我们可以在创建对象后修改其属性。

![](img/b1c904e774b84edc564f31676f4d3892_239.png)

![](img/b1c904e774b84edc564f31676f4d3892_241.png)

![](img/b1c904e774b84edc564f31676f4d3892_243.png)

![](img/b1c904e774b84edc564f31676f4d3892_245.png)

![](img/b1c904e774b84edc564f31676f4d3892_247.png)

![](img/b1c904e774b84edc564f31676f4d3892_249.png)

![](img/b1c904e774b84edc564f31676f4d3892_251.png)

---

![](img/b1c904e774b84edc564f31676f4d3892_253.png)

![](img/b1c904e774b84edc564f31676f4d3892_254.png)

![](img/b1c904e774b84edc564f31676f4d3892_256.png)

![](img/b1c904e774b84edc564f31676f4d3892_258.png)

## 修改对象属性

![](img/b1c904e774b84edc564f31676f4d3892_260.png)

![](img/b1c904e774b84edc564f31676f4d3892_262.png)

![](img/b1c904e774b84edc564f31676f4d3892_264.png)

![](img/b1c904e774b84edc564f31676f4d3892_266.png)

![](img/b1c904e774b84edc564f31676f4d3892_268.png)

![](img/b1c904e774b84edc564f31676f4d3892_270.png)

使用设置器方法，我们可以修改 `emp1` 对象的属性。

![](img/b1c904e774b84edc564f31676f4d3892_271.png)

![](img/b1c904e774b84edc564f31676f4d3892_272.png)

![](img/b1c904e774b84edc564f31676f4d3892_274.png)

![](img/b1c904e774b84edc564f31676f4d3892_276.png)

![](img/b1c904e774b84edc564f31676f4d3892_278.png)

![](img/b1c904e774b84edc564f31676f4d3892_279.png)

![](img/b1c904e774b84edc564f31676f4d3892_281.png)

![](img/b1c904e774b84edc564f31676f4d3892_282.png)

```python
emp1.set_ID(2345)
emp1.set_first_name("Tina")
emp1.set_last_name("Smith")
emp1.set_salary(36000)
```

![](img/b1c904e774b84edc564f31676f4d3892_284.png)

![](img/b1c904e774b84edc564f31676f4d3892_286.png)

![](img/b1c904e774b84edc564f31676f4d3892_288.png)

![](img/b1c904e774b84edc564f31676f4d3892_290.png)

![](img/b1c904e774b84edc564f31676f4d3892_291.png)

![](img/b1c904e774b84edc564f31676f4d3892_293.png)

![](img/b1c904e774b84edc564f31676f4d3892_294.png)

修改后，再次调用 `display` 方法查看更新后的信息。

![](img/b1c904e774b84edc564f31676f4d3892_295.png)

![](img/b1c904e774b84edc564f31676f4d3892_296.png)

![](img/b1c904e774b84edc564f31676f4d3892_298.png)

![](img/b1c904e774b84edc564f31676f4d3892_300.png)

![](img/b1c904e774b84edc564f31676f4d3892_301.png)

![](img/b1c904e774b84edc564f31676f4d3892_303.png)

```python
emp1.display()
```

![](img/b1c904e774b84edc564f31676f4d3892_305.png)

![](img/b1c904e774b84edc564f31676f4d3892_307.png)

![](img/b1c904e774b84edc564f31676f4d3892_309.png)

![](img/b1c904e774b84edc564f31676f4d3892_310.png)

---

![](img/b1c904e774b84edc564f31676f4d3892_312.png)

![](img/b1c904e774b84edc564f31676f4d3892_314.png)

![](img/b1c904e774b84edc564f31676f4d3892_316.png)

![](img/b1c904e774b84edc564f31676f4d3892_317.png)

![](img/b1c904e774b84edc564f31676f4d3892_319.png)

![](img/b1c904e774b84edc564f31676f4d3892_320.png)

![](img/b1c904e774b84edc564f31676f4d3892_322.png)

## 总结

![](img/b1c904e774b84edc564f31676f4d3892_323.png)

![](img/b1c904e774b84edc564f31676f4d3892_324.png)

![](img/b1c904e774b84edc564f31676f4d3892_326.png)

![](img/b1c904e774b84edc564f31676f4d3892_328.png)

![](img/b1c904e774b84edc564f31676f4d3892_330.png)

在本节课中，我们一起学习了以下内容：

![](img/b1c904e774b84edc564f31676f4d3892_332.png)

![](img/b1c904e774b84edc564f31676f4d3892_334.png)

![](img/b1c904e774b84edc564f31676f4d3892_336.png)

![](img/b1c904e774b84edc564f31676f4d3892_337.png)

1.  **创建类与构造函数**：我们创建了一个 `Employee` 类，并通过 `*args` 实现了灵活的构造函数，以支持默认值和自定义值的初始化。
2.  **定义显示方法**：我们创建了 `display` 方法，用于打印对象的属性，并使用 `\n` 使输出更清晰。
3.  **创建与测试对象**：我们实例化了两个员工对象，并验证了构造函数的行为。
4.  **实现设置器与获取器**：我们编写了设置器和获取器方法，以便在对象创建后修改和访问其属性。
5.  **修改对象属性**：我们使用设置器方法成功修改了对象的属性，并验证了修改结果。

![](img/b1c904e774b84edc564f31676f4d3892_339.png)

![](img/b1c904e774b84edc564f31676f4d3892_341.png)

![](img/b1c904e774b84edc564f31676f4d3892_343.png)

![](img/b1c904e774b84edc564f31676f4d3892_344.png)

通过这些步骤，我们掌握了Python中类的创建、对象初始化、方法定义以及属性访问与修改的基本操作。这些知识是面向对象编程的核心，将帮助你在实际项目中更好地组织和管理代码。