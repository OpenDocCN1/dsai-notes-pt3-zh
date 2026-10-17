
Next, how much does the output of \( o_1 \) change with respect to its total net input?

The partial <u>derivative of the logistic function</u> is the output multiplied by 1 minus the output:

$$ out_{o1} = \frac{1}{1+e^{-net_{o1}}} $$

$$ \frac{\partial out_{o1}}{\partial net_{o1}} = out_{o1}(1 - out_{o1}) = 0.75136507(1 - 0.75136507) = 0.186815602 $$

Finally, how much does the total net input of \( o_1 \) change with respect to \( w_5 \)?

$$ net_{o1} = w_5 * out_{h1} + w_6 * out_{h2} + b_2 * 1 $$

$$ \frac{\partial net_{o1}}{\partial w_5} = 1 * out_{h1} * w_5^{(1-1)} + 0 + 0 = out_{h1} = 0.593269992 $$

Putting it all together:

$$ \frac{\partial E_{total}}{\partial w_5} = \frac{\partial E_{total}}{\partial out_{o1}} * \frac{\partial out_{o1}}{\partial net_{o1}} * \frac{\partial net_{o1}}{\partial w_5} $$

$$ \frac{\partial E_{total}}{\partial w_5} = 0.74136507 * 0.186815602 * 0.593269992 = 0.082167041 $$

To decrease the error, we then subtract this value from the current weight (optionally multiplied by some learning rate, eta, which we'll set to 0.5):

$$ w_5^+ = w_5 - \eta * \frac{\partial E_{total}}{\partial w_5} = 0.4 - 0.5 * 0.082167041 = 0.35891648 $$

## Backpropagation

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_220_0.png)

**Fig. 1** Overview of backpropagation. (a) Training pattern is fed forward, generating corresponding output. (b) Error between actual and desired output is computed. (c) The error propagates back, through updates where a ratio of the gradient \(\frac{\partial E}{\partial w_i}\) is subtracted from each weight. \(x_i\), \(w_i\), \(\phi\) are the inputs, input weights, and activation function of a neuron. Error _E_ is computed from output _y_ and desired output _t_. \(\eta\) is the learning rate.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_221_0.png)

- Input Layer
- Hidden Layer
- Output Layer
- Weight

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_221_1.png)

In = α * a + β * b
Out = Sigmoid(In)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_224_0.png)

$$ In_{o_1} = w_5 * h_1 + w_7 * h_2 $$

$$ o_1 = Out_{o_1} = Sigmoid(In_{o_1}) $$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_225_0.png)

$$ In_{o_2} = w_6 * h_1 + w_8 * h_2 $$

$$ o_2 = Out_{o_2} = Sigmoid(In_{o_2}) $$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_226_0.png)

$$ Error = \sum_{i=1}^{2} \frac{1}{2}(z_i-o_i)^2 $$

\( z_i \) is the ground truth label

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_227_0.png)

$$ In_{h_1}=w_1*x_1+w_3*x_2 $$

$$ In_{h_2}=w_2*x_1+w_4*x_2 $$

$$ In_{o_1}=w_5*h_1+w_7*h_2 $$

$$ In_{o_2}=w_6*h_1+w_8*h_2 $$

$$ h_1=Out_{h_1}=Sigmoid(In_{h_1}) $$

$$ h_2=Out_{h_2}=Sigmoid(In_{h_2}) $$

$$ o_1=Out_{o_1}=Sigmoid(In_{o_1}) $$

$$ o_2=Out_{o_2}=Sigmoid(In_{o_2}) $$

$$ Error=\sum_{i=1}^{2}\frac{1}{2}(z_i-o_i)^2 $$

## Backward Propagation

### Update of W₅₋₈

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_229_0.png)

**1. Gradient Computation**

$$ \delta_5 = \frac{\partial Error}{\partial w_5} = \frac{\partial Error}{\partial o_1} * \frac{\partial o_1}{\partial In_{o_1}} * \frac{\partial In_{o_1}}{\partial w_5} $$

where,

$$ \frac{\partial Error}{\partial o_1} = z_1 - o_1 $$

$$ \frac{\partial o_1}{\partial In_{o_1}} = o_1 * (1 - o_1) $$

$$ \frac{\partial In_{o_1}}{\partial w_5} = h_1 $$

**2. Update weight**

$$ w'_5 = w_5 - \eta * \delta_5 $$

### Update of W<sub>1~4</sub>

**1. Gradient Computation**

$$ \delta_1 = \frac{\partial Error}{\partial w_1} = \frac{\partial Error}{\partial o_1} * \frac{\partial o_1}{\partial w_1} + \frac{\partial Error}{\partial o_2} * \frac{\partial o_2}{\partial w_1} $$

$$ = \frac{\partial Error}{\partial o_1} * \frac{\partial o_1}{\partial In_{o_1}} * \frac{\partial In_{o_1}}{\partial h_1} * \frac{\partial h_1}{\partial In_{h_1}} * \frac{\partial In_{h_1}}{\partial w_1} + \frac{\partial Error}{\partial o_2} * \frac{\partial o_2}{\partial In_{o_2}} * \frac{\partial In_{o_2}}{\partial h_1} * \frac{\partial h_1}{\partial In_{h_1}} * \frac{\partial In_{h_1}}{\partial w_1} $$

where,

$$ \frac{\partial Error}{\partial o_1} = z_1 - o_1 $$

$$ \frac{\partial o_1}{\partial In_{o_1}} = o_1 * (1 - o_1) \quad \frac{\partial In_{o_1}}{\partial h_1} = w_5 $$

$$ \frac{\partial h_1}{\partial In_{h_1}} = h_1 * (1 - h_1) $$

$$ \frac{\partial In_{h_1}}{\partial w_1} = x_1 $$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_230_0.png)
