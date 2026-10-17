# # Backpropagation

Backpropagation: a simple example

\( f(x, y, z) = (x + y)z \)

e.g. x = -2, y = 5, z = -4

+   \( q = x + y \quad \frac{\partial q}{\partial x} = 1, \frac{\partial q}{\partial y} = 1 \)

+   \( f = qz \quad \frac{\partial f}{\partial q} = z, \frac{\partial f}{\partial z} = q \)

Want: \( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \)

![](bbox=[0.488, 0.316, 0.988, 0.656])