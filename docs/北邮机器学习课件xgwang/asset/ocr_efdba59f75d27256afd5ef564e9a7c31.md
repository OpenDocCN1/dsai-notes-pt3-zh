# Unsupervised DA method: iCAN (2.2)

Collaborative and Adversarial Network (CAN) through domain-collaborative and domain adversarial training of neural networks.

+   - Domain informative representations: from lower blocks through collaborative learning
+   - Domain uninformative representations: from higher blocks through adversarial learning.

![](bbox=[0.02, 0.48, 0.62, 0.88])

1 min_{θ,w} (1/N) Σ_{i=1}^N L_D(D(F(x_i; θ); w), d_i)
2 max_θ min_w (1/N) Σ_{i=1}^N L_D(D(F(x_i; θ); w), d_i)
3 min_{Θ_F, λ} L_CAN = Σ_{k=1}^{m-1} λ_k min_{w_k} L_D(θ_k, w_k) + λ_m min_{w_m} L_D(θ_m, w_m), s.t. Σ_{k=1}^{m-1} λ_k = λ_0, |λ_k| ≤ λ_0

> [9] W. Zhang, W. Ouyang, W. Li, and D. Xu. Collaborative and adversarial network for unsupervised domain adaptation. In CVPR, pages 3801–3809, 2018.