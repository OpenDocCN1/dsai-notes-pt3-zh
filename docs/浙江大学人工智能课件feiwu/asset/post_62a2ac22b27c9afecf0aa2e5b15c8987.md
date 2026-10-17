
## Backpropagation

### Backpropagation: a simple example

$f(x, y, z) = (x + y)z$

e.g. $x = -2$, $y = 5$, $z = -4$

$q = x + y \qquad \frac{\partial q}{\partial x} = 1,\ \frac{\partial q}{\partial y} = 1$

$f = qz \qquad \frac{\partial f}{\partial q} = z,\ \frac{\partial f}{\partial z} = q$

Want: $\frac{\partial f}{\partial x},\ \frac{\partial f}{\partial y},\ \frac{\partial f}{\partial z}$

Chain rule:
$\frac{\partial f}{\partial y} = \frac{\partial f}{\partial q} * \frac{\partial q}{\partial y}$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1145_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1146_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1147_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1148_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1149_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1150_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1151_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1151_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1152_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1153_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1154_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1155_0.png)
