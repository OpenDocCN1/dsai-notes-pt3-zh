# Vanishing and exploding gradients

梯度消失/爆炸问题

+   - Training a very deep net makes the problem even more serious, since after BP through many layers, the gradients become either very small or very large
+   - In very deep nets and recurrent nets, the final output is composed of a large number of non-linear transformations
+   - Even though each of these non-linear stages may be relatively smooth, their composition is going to be much "more non-linear", in the sense that the derivatives through the whole composition will tend to be either very small or very large, with more ups and downs

![](bbox=[0.18, 0.55, 0.85, 0.7])

When composing many non-linearities (like the activation non-linearity in a deep or recurrent neural network), the result is highly non-linear, typically with most of the values associated with a tiny derivative, some values with a large derivative, and many ups and downs (not shown here)