# RCNNs to represent conditional distributions P(y|x)

+   - The input x is a sequence of the same length as the output sequence y
+   - Removing the dash lines, it assumes y_i are independent of each other when the past input sequence is given, i.e. P(y_i|y_1,...,y_{i-1},x_1,...,x_{i-1}) = P(y_i|x_i,...,x_{i-1})
+   - Without the conditional independence assumption, add the dash lines and the prediction of y_{t-1} is based on both the past x's and past y's

![](bbox=[0.12, 0.48, 0.88, 0.88])