# Stochastic backpropagation

# Algorithm 1 (Stochastic backpropagation)

```
1 begin initialize network topology (# hidden units), w, criterion θ, η, m ← 0
2 do m ← m + 1
3 X^m ← randomly chosen pattern
4 w_ij ← w_ij + ηδ_j x_i; w_jk ← w_jk + ηδ_k y_j
5 until ΔJ(w) < θ
6 return w
7 end
```

> (Duda et al. Pattern Classification 2000)

+   - In stochastic training, a weight update may reduce the error on the single pattern being presented, yet increase the error on the full training set.