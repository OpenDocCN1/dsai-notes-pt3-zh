# 19：条件控制循环（while）构建 🔄

![](img/095ec7319324d6904e446940a0879b5c_0.png)

![](img/095ec7319324d6904e446940a0879b5c_2.png)

在本节课中，我们将学习 Python 中的 **`while` 循环**。`while` 循环是一种条件控制循环，它允许我们重复执行一段代码，只要指定的条件为真。我们将通过几个示例来理解其工作原理、语法结构以及如何避免常见错误，例如无限循环。

![](img/095ec7319324d6904e446940a0879b5c_4.png)

![](img/095ec7319324d6904e446940a0879b5c_5.png)

---

## 什么是 `while` 循环？ 🤔

![](img/095ec7319324d6904e446940a0879b5c_7.png)

`while` 循环用于**重复执行一组指令或代码行**，只要指定的条件为真。当 `while` 条件变为假时，循环停止执行。如果 `while` 条件从未为真，则循环永远不会执行。

![](img/095ec7319324d6904e446940a0879b5c_9.png)

![](img/095ec7319324d6904e446940a0879b5c_10.png)

其核心逻辑可以用以下伪代码表示：

![](img/095ec7319324d6904e446940a0879b5c_11.png)

```
while 条件为真:
    执行代码块
```

![](img/095ec7319324d6904e446940a0879b5c_13.png)

![](img/095ec7319324d6904e446940a0879b5c_14.png)

![](img/095ec7319324d6904e446940a0879b5c_15.png)

---

![](img/095ec7319324d6904e446940a0879b5c_17.png)

![](img/095ec7319324d6904e446940a0879b5c_18.png)

## 示例演示：基础 `while` 循环

![](img/095ec7319324d6904e446940a0879b5c_20.png)

![](img/095ec7319324d6904e446940a0879b5c_21.png)

上一节我们介绍了 `while` 循环的基本概念，本节中我们来看看具体的代码示例。

![](img/095ec7319324d6904e446940a0879b5c_23.png)

![](img/095ec7319324d6904e446940a0879b5c_24.png)

### 示例 1：从 0 计数到 9

![](img/095ec7319324d6904e446940a0879b5c_26.png)

以下是创建一个从 0 开始计数到 9 的程序：

![](img/095ec7319324d6904e446940a0879b5c_28.png)

![](img/095ec7319324d6904e446940a0879b5c_29.png)

```python
count = 0
while count < 10:
    print("count is", count)
    count += 1
```

![](img/095ec7319324d6904e446940a0879b5c_31.png)

![](img/095ec7319324d6904e446940a0879b5c_32.png)

**代码解释：**
1.  我们创建了一个整数变量 `count` 并将其初始值设为 `0`。
2.  循环条件是 `while count < 10`。只要 `count` 的值小于 10，循环就会继续。
3.  在循环体内，我们打印当前 `count` 的值，然后使用 `count += 1` 将 `count` 的值增加 1。
4.  当 `count` 增加到 10 时，条件 `10 < 10` 为假，循环停止。

![](img/095ec7319324d6904e446940a0879b5c_34.png)

![](img/095ec7319324d6904e446940a0879b5c_36.png)

运行此程序将输出：
```
count is 0
count is 1
...
count is 9
```

![](img/095ec7319324d6904e446940a0879b5c_38.png)

---

![](img/095ec7319324d6904e446940a0879b5c_40.png)

### 示例 2：以步长 2 递增

![](img/095ec7319324d6904e446940a0879b5c_42.png)

![](img/095ec7319324d6904e446940a0879b5c_43.png)

![](img/095ec7319324d6904e446940a0879b5c_44.png)

现在，我们来看一个以不同步长递增的循环。

![](img/095ec7319324d6904e446940a0879b5c_46.png)

以下是创建一个从 0 开始、每次增加 2 直到小于 10 的程序：

![](img/095ec7319324d6904e446940a0879b5c_48.png)

![](img/095ec7319324d6904e446940a0879b5c_49.png)

```python
count2 = 0
while count2 < 10:
    print(count2)
    count2 += 2
```

![](img/095ec7319324d6904e446940a0879b5c_50.png)

![](img/095ec7319324d6904e446940a0879b5c_52.png)

![](img/095ec7319324d6904e446940a0879b5c_54.png)

**代码解释：**
1.  变量 `count2` 从 0 开始。
2.  循环条件同样是 `count2 < 10`。
3.  在每次迭代中，我们打印 `count2` 的当前值，然后使用 `count2 += 2` 将其值增加 2。这是一种简写，等同于 `count2 = count2 + 2`。
4.  循环将输出 `0, 2, 4, 6, 8`。当 `count2` 变为 10 时，条件不再满足，循环结束。

![](img/095ec7319324d6904e446940a0879b5c_56.png)

---

![](img/095ec7319324d6904e446940a0879b5c_58.png)

![](img/095ec7319324d6904e446940a0879b5c_59.png)

## 需要警惕：无限循环 ⚠️

![](img/095ec7319324d6904e446940a0879b5c_61.png)

![](img/095ec7319324d6904e446940a0879b5c_63.png)

在编写 `while` 循环时，必须确保循环条件最终会变为假，否则将创建**无限循环**。

![](img/095ec7319324d6904e446940a0879b5c_65.png)

以下是无限循环的一个例子：

![](img/095ec7319324d6904e446940a0879b5c_67.png)

![](img/095ec7319324d6904e446940a0879b5c_68.png)

```python
while True:
    print("infinite loop")
```

在这个例子中，条件 `True` 永远为真，因此 `print` 语句会无限重复执行，直到程序被强制停止（例如，点击停止按钮）。除非程序确实需要永不停止（如某些服务器程序），否则应避免这种情况。确保循环体内有改变条件的语句，使循环能够正常终止。

![](img/095ec7319324d6904e446940a0879b5c_70.png)

![](img/095ec7319324d6904e446940a0879b5c_71.png)

![](img/095ec7319324d6904e446940a0879b5c_72.png)

![](img/095ec7319324d6904e446940a0879b5c_73.png)

---

![](img/095ec7319324d6904e446940a0879b5c_75.png)

## 进阶应用：`while` 循环与 `else` 语句

![](img/095ec7319324d6904e446940a0879b5c_76.png)

`while` 循环可以与 `else` 语句结合使用。`else` 块中的代码会在循环**条件自然变为假后**执行。但是，如果循环是通过 `break` 语句**提前退出**的，则 `else` 块不会执行。

![](img/095ec7319324d6904e446940a0879b5c_78.png)

![](img/095ec7319324d6904e446940a0879b5c_79.png)

让我们通过一个模拟洗衣机运行的程序来理解这一点。

### 示例 3：模拟洗衣机（自然结束）

```python
machine_on = True
door_locked = True
time_limit_count = 1
rotations_per_minute = 0

time_limit = int(input("Enter time limit for wash (minutes): "))
time_remaining = time_limit

while door_locked and machine_on and time_remaining > 0:
    rotations_per_minute += 50
    time_remaining -= time_limit_count
    print(time_remaining, "minutes left")

else:
    print("Machine powering down.")

print("Number of cycles executed:", rotations_per_minute // 50)
```

**程序流程：**
1.  设置初始状态：机器开启、门已锁、时间计数器为 1 分钟/次、转速为 0。
2.  用户输入洗涤时间限制（例如 20 分钟）。
3.  `while` 循环条件：门锁着、机器开着且剩余时间大于 0。
4.  循环体内：每次迭代增加转速，减少剩余时间，并打印剩余时间。
5.  当 `time_remaining` 变为 0 时，循环条件自然变为假。
6.  由于是自然结束，程序会执行 `else` 块，打印 “Machine powering down.”。
7.  最后，打印执行的总周期数。

---

### 示例 4：模拟洗衣机（使用 `break` 提前结束）

如果我们在循环中使用了 `break` 语句，情况会有所不同。

```python
# ... (前面的变量初始化与输入部分与示例3相同) ...

while door_locked and machine_on and time_remaining > 0:
    rotations_per_minute += 50
    time_remaining -= time_limit_count
    print(time_remaining, "minutes left")
    break  # 在第一轮迭代后立即中断循环

else:
    print("Machine powering down.")  # 这行不会被执行

print("Number of cycles executed:", rotations_per_minute // 50)
```

![](img/095ec7319324d6904e446940a0879b5c_81.png)

**程序流程：**
1.  循环开始，执行一次迭代。
2.  遇到 `break` 语句，**立即退出** `while` 循环。
3.  由于循环是**非自然**（被`break`打断）结束的，`else` 块**被跳过**，不会执行。
4.  程序直接执行最后的 `print` 语句。

这演示了 `while...else` 结构中，`else` 仅在循环条件自然失效时才执行的特点。

![](img/095ec7319324d6904e446940a0879b5c_83.png)

---

## 总结 📝

本节课中我们一起学习了 Python 的 `while` 循环：

1.  **基本语法**：`while` 循环在指定条件为真时重复执行代码块。
2.  **核心要点**：必须在循环体内修改条件相关的变量，以确保循环能正常终止，避免无限循环。
3.  **递增操作**：学习了 `+=` 运算符这种简洁的变量递增方式。
4.  **`while...else` 结构**：`else` 子句仅在循环条件**自然变为假**后执行；如果循环被 `break` 语句中断，`else` 块则不会执行。

通过理解这些概念和示例，你已经掌握了使用 `while` 循环来构建根据条件重复执行任务程序的基本技能。