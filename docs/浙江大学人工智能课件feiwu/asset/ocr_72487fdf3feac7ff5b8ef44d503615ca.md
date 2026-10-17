# # Vanilla RNN vs LSTM

# # Vanilla RNN Gradient Flow

![](bbox=[0.119, 0.3, 0.369, 0.565])

Backpropagation from h<sub>t</sub> to h<sub>t-1</sub> multiplies by W<sub>hh</sub>

h<sub>t</sub> = tanh(W<sub>hh</sub>h<sub>t-1</sub> + W<sub>xh</sub>x<sub>t</sub>)

= tanh \left( \begin{pmatrix} W_{hh} & W_{hx} \end{pmatrix} \begin{pmatrix} h_{t-1} \\ x_t \end{pmatrix} \right)

= tanh \left( W \begin{pmatrix} h_{t-1} \\ x_t \end{pmatrix} \right)

![](bbox=[0.504, 0.3, 0.994, 0.798])

a<sup>(t)</sup> = b + Wh<sup>(t-1)</sup> + Ux<sup>(t)</sup>

h<sup>(t)</sup> = tanh(a<sup>(t)</sup>)

o<sup>(t)</sup> = c + Vh<sup>(t)</sup>

y<sup>(t)</sup> = softmax(o<sup>(t)</sup>)

> Bengio et al. "Learning long-term dependencies with gradient descent is difficult". IEEE Transactions on Neural Networks, 1994
> Pascanu et al. "On the difficulty of training recurrent neural networks", ICML 2013