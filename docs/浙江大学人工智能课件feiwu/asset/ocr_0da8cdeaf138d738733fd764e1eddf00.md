# # Gradient Descent

```
```python
# Vanilla Gradient Descent

while True:
    weights_grad = evaluate_gradient(loss_fun, data, weights)
    weights += - step_size * weights_grad  # perform parameter update
```
```

![](bbox=[0.163, 0.443, 0.722, 0.942])