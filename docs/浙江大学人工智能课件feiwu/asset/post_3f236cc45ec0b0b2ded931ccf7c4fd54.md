

# Representation Power

Neural Networks with fully-connected layers define a family of functions that are parameterized by the weights of the network.

It turns out that Neural Networks with at least one hidden layer are *universal approximators*. That is, it can be shown (e.g. see *Approximation by Superpositions of Sigmoidal Function* from 1989 (pdf), or this intuitive explanation from Michael Nielsen) that given any continuous function $f(x)$ and some $\epsilon > 0$, there exists a Neural Network $g(x)$ with one hidden layer (with a reasonable choice of non-linearity, e.g. sigmoid) such that $\forall x,\ |f(x)-g(x)| < \epsilon$. In other words, the neural network can approximate any continuous function.

If one hidden layer suffices to approximate any function, why use more layers and go deeper? The answer is that the fact that a two-layer Neural Network is a universal approximator is, while mathematically cute, a relatively weak and useless statement in practice. In one dimension, the “sum of indicator bumps” function $g(x)=\sum_i c_i\mathbf{1}(a_i < x < b_i)$ where $a,b,c$ are parameter vectors is also a universal approximator, but no one would suggest that we use this functional form in Machine Learning. Neural Networks work well in practice because they compactly express nice, smooth functions that fit well with the statistical properties of data we encounter in practice, and are also easy to learn using our optimization algorithms (e.g. gradient descent). Similarly, the fact that deeper networks (with multiple hidden layers) can work better than a single-hidden-layer networks is an empirical observation, despite the fact that their representational power is equal.

# Representation Power

## universal approximation theorem

A **feed-forward** network with a single hidden layer containing a finite number of **neurons** (i.e., a **multilayer perceptron**), can approximate **continuous functions** on **compact subsets** of Rⁿ, under mild assumptions on the activation function. The theorem thus states that simple neural networks can _represent_ a wide variety of interesting functions when given appropriate parameters; however, it does not touch upon the algorithmic **learnability** of those parameters. One of the first versions of the **theorem** was proved by **George Cybenko** in 1989 for **sigmoid** activation functions.

- Balázs Csanád Csáji, Approximation with Artificial Neural Networks, Faculty of Sciences; Eötvös Loránd University, Hungary
- Cybenko, G., Approximations by superpositions of sigmoidal functions, _Mathematics of Control, Signals, and Systems_, 2 (4), 303-31, 1989
- Kurt Hornik, Approximation Capabilities of Multilayer Feedforward Networks, _Neural Networks_, 4(2), 251–257, 1991

# Representation Power

We increase the size and number of layers in a Neural Network, the **capacity** of the network increases. That is, the space of representable functions grows since the neurons can collaborate to express many different functions

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1121_0.png)

Larger Neural Networks can represent more complicated functions. The data are shown as circles colored by their class, and the decision regions by a trained neural network are shown underneath.

Overfitting occurs with 20 hidden neurons

# Artificial Intelligence
# Optimization and Gradient Descent

# Problem

- How to learn the best W of a classifier?
  - We have some dataset of (x,y)
  - We have a score function: $s = f(x) = W\phi(x)$
  - We have a loss function: softmax, svm…

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1123_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1123_1.png)

# Optimization

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1124_0.png)

# Optimization

- Strategy #1:

- A first very bad idea solution: Random search

```python
# assume X_train is the data where each column is an example (e.g. 3073 x 50,000)
# assume Y_train are the labels (e.g. 1D array of 50,000)
# assume the function L evaluates the loss function
bestloss = float("inf") # Python assigns the highest possible float value
for num in xrange(1000):
    W = np.random.randn(10, 3073) * 0.0001 # generate random parameters
    loss = L(X_train, Y_train, W) # get the loss over the entire training set
    if loss < bestloss: # keep track of the best solution
        bestloss = loss
        bestW = W
    print 'in attempt %d the loss was %f, best %f' % (num, loss, bestloss)

# prints:
# in attempt 0 the loss was 9.401632, best 9.401632
# in attempt 1 the loss was 8.959668, best 8.959668
# in attempt 2 the loss was 9.044034, best 8.959668
# in attempt 3 the loss was 9.278948, best 8.959668
# in attempt 4 the loss was 8.857370, best 8.857370
# in attempt 5 the loss was 8.943151, best 8.857370
# in attempt 6 the loss was 8.605604, best 8.605604
# ... (truncated: continues for 1000 lines)
```

