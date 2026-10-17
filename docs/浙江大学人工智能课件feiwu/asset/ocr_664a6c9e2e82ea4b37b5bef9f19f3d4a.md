# # Vanilla RNN vs LSTM

# ## Vanilla RNN Gradient Flow

Bengio et al, “Learning long-term dependencies with gradient descent is difficult”, IEEE Transactions on Neural Networks, 1994  
Pascanu et al, “On the difficulty of training recurrent neural networks”, ICML 2013

![](bbox=[0.031, 0.298, 0.435, 0.591])

**Backpropagation from $h_t$ to $h_{t-1}$ multiplies by $W_{hh}$**

$$h_t = \tanh(W_{hh}h_{t-1} + W_{xh}x_t)$$

$$= \tanh\left(\begin{pmatrix}W_{hh} & W_{hx}\end{pmatrix}\begin{pmatrix}h_{t-1}\\x_t\end{pmatrix}\right)$$

$$= \tanh\left(W\begin{pmatrix}h_{t-1}\\x_t\end{pmatrix}\right)$$

![](bbox=[0.482, 0.306, 0.995, 0.785])

$$a^{(t)} = b + Wh^{(t-1)} + Ux^{(t)}$$
$$h^{(t)} = \tanh(a^{(t)})$$
$$o^{(t)} = c + Vh^{(t)}$$
$$y^{(t)} = \operatorname{softmax}(o^{(t)})$$