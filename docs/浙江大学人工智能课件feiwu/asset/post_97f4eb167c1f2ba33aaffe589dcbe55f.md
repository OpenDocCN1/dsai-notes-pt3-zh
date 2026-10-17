

# Encoder-Decoder Sequence-to-Sequence Architectures

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_384_0.png)

Figure 10.12: Example of an encoder-decoder or sequence-to-sequence RNN architecture, for learning to generate an output sequence $(y^{(1)},\ldots,y^{(n_y)})$ given an input sequence $(x^{(1)},x^{(2)},\ldots,x^{(n_x)})$. It is composed of an encoder RNN that reads the input sequence as well as a decoder RNN that generates the output sequence (or computes the probability of a given output sequence). The final hidden state of the encoder RNN is used to compute a generally fixed-size context variable $C$, which represents a semantic summary of the input sequence and is given as input to the decoder RNN.

# Training a RNN with Gradient Flow

there is a loss at each timestep since a prediction is made at each timestep.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_386_0.png)

$$\hat{y}^{(t)} = \operatorname{softmax}(c + Vh^{(t)})$$
$$h^{(t)} = \tanh(b + Wh^{(t-1)} + Ux^{(t)})$$

$$s_t = \tanh(Wx_t + Us_{t-1})$$
$$s_2 = \tanh(Wx_2 + Us_1)$$
$$s_0 = \tanh(Wx_0)$$

# Training a RNN with Gradient Flow

there is a loss at each timestep since a prediction is made at each timestep.

## sum the losses across time

loss at time \( t = J_t(\Theta) \)

total loss = \( J(\Theta) = \sum_t J_t(\Theta) \)

we sum gradients across time for each parameter \( P \):

\( \frac{\partial J}{\partial P} = \sum_t \frac{\partial J_t}{\partial P} \)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_387_0.png)

# Training a RNN with Gradient Flow

let’s try it out for W with the chain rule

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_388_0.png)

$$\frac{\partial J}{\partial W}=\sum_t\frac{\partial J_t}{\partial W}$$

so let’s take a single timestep $t$:

$$\frac{\partial J_2}{\partial W}=\frac{\partial J_2}{\partial y_2}\frac{\partial y_2}{\partial s_2}\frac{\partial s_2}{\partial W}$$

but wait...

$$s_2=\tanh(Us_1+Wx_2)$$

$s_1$ also depends on $W$ so we can’t just treat $\frac{\partial s_2}{\partial W}$ as a constant!

$$s_2=\tanh(Wx_2+Us_1)=\tanh(Wx_2+U\tanh(Wx_1+Us_0))$$

$$s_0=\tanh(Wx_0)$$

# Training a RNN with Gradient Flow

## how does \(s_2\) depend on W?

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_389_0.png)

\(s_2 = \tanh(Wx_2 + Us_1) = \tanh(Wx_2 + U \tanh(Wx_1 + Us_0))\)

\(s_0 = \tanh(Wx_0)\)

\(\frac{\partial s_2}{\partial W}\)

\(+ \frac{\partial s_2}{\partial s_1} \frac{\partial s_1}{\partial W}\)

\(+ \frac{\partial s_2}{\partial s_0} \frac{\partial s_0}{\partial W}\)

# Training a RNN with Gradient Flow

backpropagation through time:

\(\frac{\partial J_2}{\partial W} = \sum_{k=0}^2 \frac{\partial J_2}{\partial y_2} \frac{\partial y_2}{\partial s_2} \frac{\partial s_2}{\partial s_k} \frac{\partial s_k}{\partial W}\)

Contributions of _W_ in previous timesteps to the error at timestep _t_

\(\frac{\partial J_t}{\partial W} = \sum_{k=0}^t \frac{\partial J_t}{\partial y_t} \frac{\partial y_t}{\partial s_t} \frac{\partial s_t}{\partial s_k} \frac{\partial s_k}{\partial W}\)

Contributions of _W_ in previous timesteps to the error at timestep _t_

\(s_t = \tanh(Wx_t + Us_{t-1})\)

\(s_2 = \tanh(Wx_2 + Us_1) = \tanh(Wx_2 + U \tanh(Wx_1 + Us_0))\)

\(s_0 = \tanh(Wx_0)\)

# Training a RNN with Gradient Flow

why are RNNs hard to train?

problem: vanishing gradient

what are each of these terms?

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_392_0.png)

$$\frac{\partial s_n}{\partial s_{n-1}}=U^T\operatorname{diag}\left[1-\tanh^2(Wx_t+Us_{n-1})\right]$$

$$s_t=\tanh(Wx_t+Us_{t-1})$$

$U$ = sampled from standard normal distribution = mostly < 1

$f$ = tanh or sigmoid so $f' < 1$

the derivative of tanh is 1-tanh²

we’re multiplying a lot of **small numbers** together.

we’re multiplying a lot of small numbers together.
errors due to further back timesteps have increasingly smaller gradients.
parameters become biased to capture shorter-term dependencies.

$$s_2=\tanh(Wx_2+Us_1)=\tanh\left(Wx_2+U\tanh(Wx_1+Us_0)\right)$$

$$s_0=\tanh(Wx_0)$$

