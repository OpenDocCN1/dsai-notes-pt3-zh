# 哈佛大学《CS50P Python编程入门》课程笔记 - P17：返回值 📝

![](img/821f662a89a060c0f46e27006d1fb7b6_0.png)

在本节课中，我们将要学习函数的一个重要概念：**返回值**。我们将了解返回值与副作用之间的区别，并探索如何使用返回值使我们的程序更加灵活和强大。

---

![](img/821f662a89a060c0f46e27006d1fb7b6_2.png)

## 函数输出的两种形式

上一节我们介绍了函数作为程序的基本构建块，可以接收输入并产生输出。本节中我们来看看，函数实际上可以产生两种输出：一种是**返回值**，另一种是**副作用**。

*   **副作用**：指函数执行时产生的即时、可见的效果，例如在屏幕上打印文本。
*   **返回值**：指函数执行后，可以传递给程序其他部分使用的一个具体**值**。

## 从副作用到返回值

让我们通过一个简单的例子来理解这个概念。假设我们有一个名为 `greet` 的函数，它根据输入内容进行回应。

最初，这个函数使用 `print` 语句直接输出结果，这是一个典型的副作用：

```python
def greet(input_str):
    if "hello" in input_str:
        print("hello there")
    else:
        print("I'm not sure what you mean")
```

当我们调用 `greet("hello, computer")` 时，它会直接在终端打印出 `hello there`。这很方便，但结果无法被程序的其他部分再次利用。

为了使函数的输出更灵活，我们可以使用 `return` 关键字将其改为返回值：

```python
def greet(input_str):
    if "hello" in input_str:
        return "hello there"
    else:
        return "I'm not sure what you mean"
```

现在，`greet` 函数不再直接打印，而是返回一个字符串值。如果我们直接运行 `greet("hello, computer")`，终端上不会显示任何内容，因为返回值被“传递”了出来，但还没有被“接收”或使用。

## 捕获和使用返回值

要使用函数的返回值，我们需要将其存储在一个变量中。以下是具体步骤：

1.  调用函数并传入参数。
2.  使用赋值运算符 `=` 将函数的返回值存储到一个变量里。

```python
# 调用 greet 函数，并将返回值存储在变量 greeting_message 中
greeting_message = greet("hello, computer")
```

现在，`greeting_message` 这个变量就包含了字符串 `"hello there"`。我们可以自由地使用这个变量，例如打印它：

```python
print(greeting_message)  # 输出：hello there
```

## 返回值的灵活性优势

返回值的真正威力在于其灵活性。一旦我们将函数的输出捕获到变量中，就可以在程序的后续部分以各种方式修改和使用它，而不仅仅是原样输出。

以下是几个展示灵活性的例子：

*   **添加前缀**：我们可以在返回值前加上其他文本。
    ```python
    print("Hmm... " + greeting_message)
    # 输出：Hmm... hello there
    ```

*   **拼接内容**：我们可以将返回值与其他字符串拼接。
    ```python
    personalized_greeting = greeting_message + ", Carter!"
    print(personalized_greeting)
    # 输出：hello there, Carter!
    ```

*   **进行判断**：我们可以根据返回值的内容做出不同的决策。
    ```python
    response = greet("how's the weather?")
    if "not sure" in response:
        print("Let me try to find out for you.")
    ```

正如你所见，返回值允许我们将函数的输出作为数据来操作，从而构建出更复杂、更动态的程序逻辑。相比之下，副作用（如直接打印）产生的是即时、一次性的效果。

---

## 本节课总结

本节课中我们一起学习了：
1.  函数可以产生两种输出：**返回值**和**副作用**。
2.  **副作用**是函数执行的即时效果（如在屏幕打印）。
3.  **返回值**是函数执行后传递出来的一个**值**，使用 `return` 关键字定义。
4.  要使用返回值，必须用变量（如 `result = function()`）将其捕获。
5.  返回值的核心优势在于**灵活性**，它允许我们在程序的任何地方修改和复用函数的输出，从而编写出更强大、更模块化的代码。

![](img/821f662a89a060c0f46e27006d1fb7b6_4.png)

![](img/821f662a89a060c0f46e27006d1fb7b6_5.png)

掌握返回值的概念是迈向编写高效、可维护Python程序的关键一步。