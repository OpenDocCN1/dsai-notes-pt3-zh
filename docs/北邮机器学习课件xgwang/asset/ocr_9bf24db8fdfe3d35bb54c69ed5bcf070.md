# Batch backpropagation

# Algorithm 2 (Batch backpropagation)

```
1 begin initialize network topology (# hidden units), w, criterion θ, η, r ← 0
2 do r ← r + 1 (increment epoch)
3 m ← 0; Δwij ← 0; Δwjk ← 0
4 do m ← m + 1
5 x^m ← select pattern
6 Δwij ← Δwij + ηδj x_i; Δwjk ← Δwjk + ηδk y_j
7 until m = n
8 wij ← wij + Δwij; wjk ← wjk + Δwjk
9 until ∇J[w] < θ
10 return w
11 end
```