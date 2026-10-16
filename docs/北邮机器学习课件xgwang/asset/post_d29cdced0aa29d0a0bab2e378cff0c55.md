
## Learning rate

- Example of linear network trained in a batch mode.

![](img/a04b187c89c5018c5ef6132980e27196_207_0.png)

- Stochastic learning with η = 0.2

![](img/a04b187c89c5018c5ef6132980e27196_208_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_208_1.png)

## Incorporation of momentum

- Error surfaces often have plateaus where there are "too many" weights (especially when the number of layers is large) and thus the error depends only weakly upon any one of them.

- Include some fraction α of the previous weight update in stochastic backpropagation

  **w(m + 1) = w(m) + (1 − α)Δw_bp(m) + αΔw(m − 1)**

  where Δw_bp(m) is the change in w(m) that would be called for by the backpropagation algorithm

  **Δw(m) = w(m) − w(m − 1)**

- Allow the network to learn more quickly when plateaus in the error surface exist.

![](img/a04b187c89c5018c5ef6132980e27196_210_0.png)

## Plateaus and cliffs

- The error surfaces of training deep neural networks include local minima, plateaus (regions where error varies only slightly as a function of weights), and cliffs (regions where the gradients rise sharply).

- Plateaus and cliffs are more important barriers to training neural networks than local minima
  - It is very difficult (or slow) to effectively update the parameters in plateaus.
  - When the parameters approach a cliff region, the gradient update step can move the learner towards a very bad configuration, ruining much progress made during recent training iterations.

![](img/a04b187c89c5018c5ef6132980e27196_211_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_211_1.png)

## Higher-order nonlinearities

- Second-order methods or momentum assume quadratic shape around the minimum. They increase the size of steps in the low-curvature directions and decrease the sizes of steps in the high-curvature directions (the steep sides of the valley).

- When training deep models, higher order derivatives introduce a lot more non-linearity, which often does not have nice symmetrical shapes that the second-order “valley” picture builds in our mind.

![](img/a04b187c89c5018c5ef6132980e27196_212_0.png)

## Gradient clipping

- To address the presence of cliffs, a useful heuristic is to clip the magnitude of the gradient, only keeping its direction if its magnitude is above a threshold (which is a hyper-parameter). This helps to avoid the destructive big moves which would happen when approaching the cliff, either from above or below.

![](img/a04b187c89c5018c5ef6132980e27196_213_0.png)

## Vanishing and exploding gradients

梯度消失/爆炸问题

- Training a very deep net makes the problem even more serious, since after BP through many layers, the gradients become either very small or very large.

- In very deep nets and recurrent nets, the final output is composed of a large number of non-linear transformations.

- Even though each of these non-linear stages may be relatively smooth, their composition is going to be much "more non-linear", in the sense that the derivatives through the whole composition will tend to be either very small or very large, with more ups and downs.

![](img/a04b187c89c5018c5ef6132980e27196_214_0.png)

When composing many non-linearities (like the activation non-linearity in a deep or recurrent neural network), the result is highly non-linear, typically with most of the values associated with a tiny derivative, some values with a large derivative, and many ups and downs (not shown here).

This arises because the Jacobian (matrix of derivatives) of a composition is the product of the Jacobian of each stage, i.e. if

\[
f = f_T \circ f_{T-1} \circ \ldots \circ f_2 \circ f_1
\]

The Jacobian matrix of derivatives of \(f(x)\) with respect to its input vector \(x\) is

\[
f' = f'_T f'_{T-1} \ldots f'_2 f'_1
\]

where

\[
f' = \frac{\partial f(x)}{\partial x}
\]

and

\[
f'_t = \frac{\partial f_t(\alpha_t)}{\partial \alpha_t}
\]

where \(\alpha_t = f_{t-1}(f_{t-2}(\ldots f_2(f_1(x))\ldots))\), i.e. composition has been replaced by matrix multiplication.
