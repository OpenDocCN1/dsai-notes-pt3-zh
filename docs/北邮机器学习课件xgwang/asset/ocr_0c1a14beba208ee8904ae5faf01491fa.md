# Underfitting

+   - The learner cannot find a solution that fits training examples well
+     - For example, use linear regression to fit training examples {x_i^(train), y_i^(train)} where y_i^(train) is an quadratic function of x_i^(train)
+   - Underfitting means the learner cannot capture some important aspects of the data
+   - Reasons for underfitting happening
+     - Model is not rich enough
+     - Difficult to find the global optimum of the objective function on the training set or easy to get stuck at local minimum
+     - Limitation on the computation resources (not enough training iterations of an iterative optimization procedure)
+   - Underfitting commonly happens in deep learning with large scale training data and could be even a more serious problem than overfitting in some cases