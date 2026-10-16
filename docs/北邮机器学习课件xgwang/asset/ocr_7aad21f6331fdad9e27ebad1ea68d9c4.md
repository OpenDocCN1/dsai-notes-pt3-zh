# Leaky units with self-connections

h_{t+1} = (1 - 1/τ) h_t + 1/τ tanh(W_{xh} x_t + W_{hh} h_t + b_h)

+   - The new value of the state h_{t+1} is a combination of linear and non-linear parts of h_t
+   - The errors are easier to be back propagated through the paths of red lines, which are linear

![](bbox=[0.15, 0.55, 0.85, 0.85])