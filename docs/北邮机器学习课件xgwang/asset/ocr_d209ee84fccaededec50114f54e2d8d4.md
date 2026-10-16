# Unsupervised DA method: DRCN (3.1)

The model is optimized through multitask learning, that is, jointly learns the (supervised) source label prediction and the (unsupervised) target data reconstruction tasks. The aim is that the encoding shared representation should learn the commonality between those tasks that provides useful information for cross-domain object recognition

![](bbox=[0.05, 0.38, 0.97, 0.78])

ℒ_c^{n_s}({Θ_enc, Θ_lab}) := Σ_{i=1}^{n_s} ℓ_c (f_c(x_i^s; {Θ_enc, Θ_lab}), y_i^s),
ℒ_r^{n_t}({Θ_enc, Θ_dec}) := Σ_{j=1}^{n_t} ℓ_r (f_r(x_j^t; {Θ_enc, Θ_dec}), x_j^t)

> [12] M. Ghifary , W.B. Kleijn , M. Zhang , D. Balduzzi , W. Li , Deep reconstruction–classification networks for unsupervised domain adaptation, in ECCV, Springer, 2016, pp. 597–613