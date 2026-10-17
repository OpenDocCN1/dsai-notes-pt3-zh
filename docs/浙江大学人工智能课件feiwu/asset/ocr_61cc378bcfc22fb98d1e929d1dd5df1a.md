# # Backpropagation

f(w,x) = 1 / (1 + e^-(w0x0 + w1x1 + w2))

σ(x) = 1 / (1 + e^-x) sigmoid function

dσ(x)/dx = e^-x / (1 + e^-x)^2 = (1 + e^-x - 1) / (1 + e^-x) * (1 / (1 + e^-x)) = (1 - σ(x))σ(x)

![](bbox=[0.176, 0.562, 0.804, 0.844])