# Stochastic backpropagation

# Algorithm 1 (Stochastic backpropagation)

```
1 begin initialize network topology (# hidden units), w, criterion θ, η, m ← 0
2 do m ← m + 1
3 x^m ← randomly chosen pattern
4 w_ij ← w_ij + η ∂J/∂w_ij; w_jk ← w_jk + η ∂J/∂w_jk
5 until ∇J(w) < θ
6 return w
7 end
```

In stochastic training, a weight update may reduce the error on the single pattern being presented, yet increase the error on the full training set.