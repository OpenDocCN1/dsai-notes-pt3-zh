# Why use a computational graph in DL?

+   - Two key strengths of computational graphs:
+     - Allow simple functions to be combined to form quite complex models
+       - A wide range of neural network models can be created by defining computational graphs consisting of simple, primitive operations.
+     - Enable **automatic differentiation**
+       - Automatic differentiation is a technique for calculating derivatives in computational graphs: once the graph has been defined using underlying primitive operations, derivatives are calculated automatically based on “local” derivatives of these operations.
+       - Gradient-based learning algorithms can be used to train NN, providing that the gradient of the loss function with respect to the parameters can be calculated efficiently.