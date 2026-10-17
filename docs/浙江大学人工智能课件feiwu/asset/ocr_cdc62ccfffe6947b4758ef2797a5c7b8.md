# # Backpropagation

# ## Another example:

\( f(w,x) = \frac{1}{1 + e^{-(w_0x_0 + w_1x_1 + w_2)}} \)

![](bbox=[0.141, 0.375, 0.883, 0.694])

[local gradient] x [upstream gradient]
[1] x [0.2] = 0.2
[1] x [0.2] = 0.2 (both inputs!)

\( f(x) = e^x \quad \rightarrow \quad \frac{df}{dx} = e^x \)
\( f_a(x) = ax \quad \rightarrow \quad \frac{df}{dx} = a \)

\( f(x) = \frac{1}{x} \quad \rightarrow \quad \frac{df}{dx} = -1/x^2 \)
\( f_c(x) = c + x \quad \rightarrow \quad \frac{df}{dx} = 1 \)