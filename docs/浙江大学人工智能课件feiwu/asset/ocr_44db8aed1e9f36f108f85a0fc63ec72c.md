# Special case of softmax

+   - If we consider a softmax function for two classes:

$$p(C_1 \mid \mathbf{x}) = \frac{\exp(a_1)}{\exp(a_1)+\exp(a_2)} = \frac{1}{1+\exp(-(a_1-a_2))} = \sigma(a_1-a_2).$$

+   - So the **logistic sigmoid** is just a special case of the **softmax function** that avoids using redundant parameters:
+     - Adding the same constant to both $a_1$ and $a_2$ has no effect.
+     - The over-parameterization of the softmax is because probabilities must add up to one.