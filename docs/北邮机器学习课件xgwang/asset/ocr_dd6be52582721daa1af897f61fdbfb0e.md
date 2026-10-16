# Generative RNN modeling P(x₁, ..., x_T)

Cost function: negative log-likelihood of x, L = Σ_t L_t

P(x) = P(x₁, ..., x_T) = ∏_{t=1}^T P(x_t | x₁, ..., x_{t-1})

L_t = - log P(x_t | x₁, ..., x_{t-1})

In generative mode, x_{t+1} is sampled from the conditional distribution P(x_{t+1} | x₁, ..., x_t) = P(x_{t+1} | z_t) (dashed arrows) and then that generated sample x_{t+1} is fed back as input for computing the next state h_{t+1}

![](bbox=[0.25, 0.7, 0.8, 0.92])