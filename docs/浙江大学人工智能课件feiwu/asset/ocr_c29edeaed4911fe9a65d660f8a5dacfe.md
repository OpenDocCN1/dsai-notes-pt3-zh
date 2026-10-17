# # ConvNet Architecture

+   - Convolutional Layer -- Summary
+     - Accepts a volume of size W₁×H₁×D₁
+     - Requires four hyperparameters:
+       - Number of filters K,
+       - their spatial extent F,
+       - the stride S,
+       - the amount of zero padding P.
+     - Produces a volume of size W₂×H₂×D₂ where:
+       - W₂=(W₁−F+2P)/S+1
+       - H₂=(H₁−F+2P)/S+1 (i.e. width and height are computed equally by symmetry)
+       - D₂=K
+     - With parameter sharing, it introduces F·F·D₁ weights per filter, for a total of (F·F·D₁)·K weights and K biases.
+     - In the output volume, the d-th depth slice (of size W₂×H₂) is the result of performing a valid convolution of the d-th filter over the input volume with a stride of S, and then offset by d-th bias.