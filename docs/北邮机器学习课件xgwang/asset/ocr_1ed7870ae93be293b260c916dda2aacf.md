# Optimization

+   - The choice of the objective function should be good for optimization
+   - Take linear regression as an example

∇_w MSE^(train) = 0
⇒ ∇_w || X^(train) w − y^(train) ||_2^2 = 0
w = (X^(train)ᵀ X^(train))⁻¹ X^(train)ᵀ y^(train)
where X^(train) = [x₁^(train), …, x_N^(train)] and y^(train) = [y₁^(train), …, y_N^(train)].