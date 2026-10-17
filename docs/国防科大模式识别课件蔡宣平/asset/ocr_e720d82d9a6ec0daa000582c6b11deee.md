d_i(\vec{x}) = ln P(ω_i) - \frac{1}{2} ln |Σ_i| - \frac{1}{2} (\vec{x} - \vec{μ_i})' Σ_i^{-1} (\vec{x} - \vec{μ_i}) \quad i = 1,2,⋯,c

# (1) 当 Σ_i = Σ 时

d_i(\vec{x}) = ln P(ω_i) - \frac{1}{2} (\vec{x} - \vec{μ_i})' Σ^{-1} (\vec{x} - \vec{μ_i})

= ln P(ω_i) - \frac{1}{2} \vec{x}' Σ^{-1} \vec{x} + \vec{μ_i}' Σ^{-1} \vec{x} - \frac{1}{2} \vec{μ_i}' Σ^{-1} \vec{μ_i}

# 当 ω_i 和 ω_j 相邻时

d_i(\vec{x}) - d_j(\vec{x}) = ln P(ω_i) - ln P(ω_j) + (\vec{μ_i} - \vec{μ_j})' Σ^{-1} \vec{x}

- \frac{1}{2} \vec{μ_i}' Σ^{-1} \vec{μ_i} + \frac{1}{2} \vec{μ_j}' Σ^{-1} \vec{μ_j} \triangleq \vec{w}_{ij}' (\vec{x} - \vec{x_0}) = 0