# Probability Recap

+   - Conditional probability  $P(x|y) = \frac{P(x,y)}{P(y)}$
+   - Product rule  $P(x,y) = P(x|y)P(y)$
+   - Chain rule  $P(X_1,X_2,\dots X_n) = P(X_1)P(X_2|X_1)P(X_3|X_1,X_2)\dots$  $= \prod_{i=1}^{n} P(X_i|X_1,\dots,X_{i-1})$
+   - X, Y independent if and only if:  $\forall x,y : P(x,y) = P(x)P(y)$
+   - X and Y are conditionally independent given Z if and only if $X \perp\!\!\perp Y|Z$  $\forall x,y,z : P(x,y|z) = P(x|z)P(y|z)$