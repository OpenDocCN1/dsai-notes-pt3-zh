# Mini-batch based stochastic gradient descent

+   - Divide the training set into mini-batches.
+   - In each epoch, randomly permute mini-batches and take a mini-batch sequentially to approximate the gradient
+     - One epoch corresponds to a single presentations of all patterns in the training set
+   - The estimated gradient at each iteration is more reliable
+   - Start with a small batch size and increase the size as training proceeds