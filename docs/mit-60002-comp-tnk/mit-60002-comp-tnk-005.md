# 005：随机游走 🚶‍♂️

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_0.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_2.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_4.png)

在本节课中，我们将要学习随机游走的概念，并通过构建模拟程序来理解其行为。我们将使用面向对象编程来创建必要的抽象，并通过数据可视化来获得对模拟结果的深入洞察。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_6.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_8.png)

## 课程概述

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_10.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_12.png)

随机游走是许多领域中的重要模型，例如股票价格波动、物理扩散过程等。通过模拟随机游走，我们可以学习如何利用计算思维来理解复杂现象。本节课程将引导我们构建一个模拟醉汉在田野中行走的程序，并逐步扩展其功能。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_14.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_16.png)

## 随机游走简介

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_18.png)

想象一个被修剪成方格纸形状的田野，一个醉汉在其中随机漫步，每隔一段时间就朝某个随机方向迈出一步。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_20.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_21.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_23.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_25.png)

我们可以提出一个问题：醉汉行走的步数与他最终距离起点的距离之间，是否存在某种有趣的关系？你可能会认为，步数越多，离起点越远；或者，由于行走是随机的，他可能会来回徘徊，始终不会走得太远。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_27.png)

为了探究这个问题，我们将通过模拟来寻找答案。

## 构建模拟：定义核心类

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_29.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_31.png)

在开始模拟之前，我们需要定义一些有用的抽象概念。我们将创建三个核心类：`Location`（位置）、`Field`（田野）和`Drunk`（醉汉）。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_33.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_34.png)

### 1. 位置类 (`Location`)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_36.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_38.png)

`Location` 类是一个不可变类型，用于表示二维空间中的一个点。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_40.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_42.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_44.png)

```python
class Location:
    def __init__(self, x, y):
        self._x = x
        self._y = y

    def get_x(self):
        return self._x

    def get_y(self):
        return self._y

    def move(self, delta_x, delta_y):
        """返回一个新的Location对象，表示移动后的位置。"""
        return Location(self._x + delta_x, self._y + delta_y)

    def dist_from(self, other):
        """计算与另一个Location对象之间的距离。"""
        x_dist = self._x - other.get_x()
        y_dist = self._y - other.get_y()
        return (x_dist**2 + y_dist**2)**0.5

    def __str__(self):
        return f'<{self._x}, {self._y}>'
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_46.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_48.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_50.png)

### 2. 醉汉基类 (`Drunk`)

`Drunk` 类是一个基类，其主要目的是被继承。它本身并不实现具体的行走逻辑。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_52.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_54.png)

```python
class Drunk:
    def __init__(self, name):
        self._name = name

    def take_step(self):
        # 将在子类中具体实现
        raise NotImplementedError

    def get_name(self):
        return self._name

    def __str__(self):
        return f'This drunk is named {self._name}'
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_56.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_58.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_60.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_62.png)

### 3. 具体醉汉子类

我们将创建两种具体的醉汉：`UsualDrunk`（普通醉汉）和 `MasochisticDrunk`（受虐狂醉汉）。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_64.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_66.png)

**普通醉汉 (`UsualDrunk`)** 会随机向四个方向（东、南、西、北）移动一个单位。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_68.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_70.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_72.png)

```python
import random

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_74.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_76.png)

class UsualDrunk(Drunk):
    def take_step(self):
        step_choices = [(0, 1), (0, -1), (1, 0), (-1, 0)]
        return random.choice(step_choices)
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_78.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_80.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_82.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_84.png)

**受虐狂醉汉 (`MasochisticDrunk`)** 的行走具有偏向性：向北走1.1步，向南走0.9步，东西方向则正常移动。这模拟了一种向上（北）的偏好。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_86.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_88.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_90.png)

```python
class MasochisticDrunk(Drunk):
    def take_step(self):
        step_choices = [(0.0, 1.1), (0.0, -0.9), (1.0, 0.0), (-1.0, 0.0)]
        return random.choice(step_choices)
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_92.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_94.png)

### 4. 田野类 (`Field`)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_96.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_98.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_100.png)

`Field` 类是一个可变类型，它使用字典来跟踪每个醉汉在田野中的当前位置。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_102.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_104.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_106.png)

```python
class Field:
    def __init__(self):
        self._drunks = {}  # 字典：醉汉 -> 位置

    def add_drunk(self, drunk, loc):
        if drunk in self._drunks:
            raise ValueError('Duplicate drunk')
        else:
            self._drunks[drunk] = loc

    def get_loc(self, drunk):
        if drunk not in self._drunks:
            raise ValueError('Drunk not in field')
        return self._drunks[drunk]

    def move_drunk(self, drunk):
        if drunk not in self._drunks:
            raise ValueError('Drunk not in field')
        x_dist, y_dist = drunk.take_step()
        current_loc = self._drunks[drunk]
        # 使用Location的move方法获得新位置
        self._drunks[drunk] = current_loc.move(x_dist, y_dist)
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_108.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_110.png)

## 实施模拟

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_112.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_114.png)

有了这些类，我们现在可以编写模拟函数。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_116.png)

### 模拟单次行走

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_118.png)

`walk` 函数模拟一个醉汉在田野中行走指定步数，并返回最终位置与起点的距离。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_120.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_122.png)

```python
def walk(field, drunk, num_steps):
    """模拟醉汉行走，返回最终距离起点的距离。"""
    start = field.get_loc(drunk)
    for _ in range(num_steps):
        field.move_drunk(drunk)
    return start.dist_from(field.get_loc(drunk))
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_124.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_125.png)

### 模拟多次试验

`sim_walks` 函数进行多次试验，收集每次行走的距离，以便进行统计分析。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_127.png)

```python
def sim_walks(num_steps, num_trials, drunk_class):
    """模拟多次试验，返回每次试验的距离列表。"""
    homer = drunk_class('Homer')  # 创建一个醉汉实例
    origin = Location(0, 0)
    distances = []
    for _ in range(num_trials):
        f = Field()
        f.add_drunk(homer, origin)
        distances.append(round(walk(f, homer, num_steps), 1))
    return distances
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_129.png)

### 运行模拟与健全性检查

在运行完整模拟之前，进行健全性检查至关重要。我们应该在一些我们知道答案的简单案例上测试我们的模拟。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_131.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_133.png)

例如，行走0步的距离应为0，行走1步的距离应为1。如果模拟结果不符合这些预期，说明代码中存在错误。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_135.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_137.png)

```python
# 健全性检查示例
print('Testing 0 steps:', sim_walks(0, 100, UsualDrunk)[:5])
print('Testing 1 step:', sim_walks(1, 100, UsualDrunk)[:5])
```

通过健全性检查后，我们可以运行更广泛的模拟，观察步数与平均距离之间的关系。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_139.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_141.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_143.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_145.png)

## 结果分析与可视化 📊

运行模拟后，我们发现对于`UsualDrunk`，平均距离似乎随着步数的平方根增长。对于`MasochisticDrunk`，由于向北的偏差，其距离增长更快，大约与步数乘以一个常数（0.05）成正比。

为了更直观地理解这些结果，我们使用 `matplotlib` 库进行数据可视化。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_147.png)

### 基本绘图

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_149.png)

以下是一个简单的绘图示例，展示如何绘制两种醉汉在不同步数下的平均距离趋势。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_151.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_153.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_155.png)

```python
import pylab

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_157.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_159.png)

# 假设我们已经有了数据
usual_distances = [...]  # UsualDrunk 的平均距离列表
maso_distances = [...]   # MasochisticDrunk 的平均距离列表
step_numbers = [...]     # 步数列表

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_161.png)

pylab.plot(step_numbers, usual_distances, 'b-', label='Usual Drunk')
pylab.plot(step_numbers, maso_distances, 'r--', label='Masochistic Drunk')
pylab.title('Mean Distance from Origin')
pylab.xlabel('Number of Steps')
pylab.ylabel('Distance from Origin')
pylab.legend()
pylab.show()
```

### 探索不同类型的田野

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_163.png)

我们可以通过继承 `Field` 类来创建更复杂的田野，例如带有“虫洞”的奇异田野。当醉汉走到虫洞位置时，会被传送到田野中的另一个随机位置。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_165.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_167.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_169.png)

```python
class OddField(Field):
    def __init__(self, num_holes=1000, x_range=100, y_range=100):
        super().__init__()
        self._wormholes = {}
        for _ in range(num_holes):
            x = random.randint(-x_range, x_range)
            y = random.randint(-y_range, y_range)
            new_x = random.randint(-x_range, x_range)
            new_y = random.randint(-y_range, y_range)
            self._wormholes[(x, y)] = Location(new_x, new_y)

    def move_drunk(self, drunk):
        super().move_drunk(drunk)  # 先进行正常移动
        loc = self.get_loc(drunk)
        if (loc.get_x(), loc.get_y()) in self._wormholes:
            # 如果当前位置是虫洞，则传送到新位置
            self._drunks[drunk] = self._wormholes[(loc.get_x(), loc.get_y())]
```

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_171.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_173.png)

可视化单次行走的路径，可以清晰地看到虫洞对行走轨迹产生的巨大影响。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_175.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_177.png)

## 课程总结

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_178.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_180.png)

在本节课中，我们一起学习了随机游走的概念及其模拟方法。我们通过构建 `Location`、`Drunk` 和 `Field` 等类，实现了对醉汉行走的模拟。我们强调了健全性检查的重要性，以确保模拟代码的正确性。通过扩展醉汉类型和田野类型，我们探究了不同因素对随机游走结果的影响。最后，我们利用数据可视化工具 `matplotlib` 将模拟结果转化为直观的图表，从而获得了更深入的洞察。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_182.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_183.png)

随机游走的模拟不仅是一个有趣的练习，更是展示如何利用计算思维、面向对象编程和数据分析来理解和解释现实世界现象的绝佳范例。