
## Unsupervised DA method: iCAN (2.2)

Collaborative and Adversarial Network (CAN) through domain-collaborative and domain adversarial training of neural networks.

- Domain informative representations: from lower blocks through collaborative learning
- Domain uninformative representations: from higher blocks through adversarial learning.

![](img/a04b187c89c5018c5ef6132980e27196_258_0.png)

1 min_{θ,w} (1/N) Σ_{i=1}^N L_D(D(F(x_i; θ); w), d_i)
2 max_θ min_w (1/N) Σ_{i=1}^N L_D(D(F(x_i; θ); w), d_i)
3 min_{θ_F, λ} L_CAN = Σ_{k=1}^{m-1} λ_k min_{w_k} L_D(θ_k, w_k) + λ_m min_{w_m} L_D(θ_m, w_m), s.t. Σ_{k=1}^{m-1} λ_k = λ_0, |λ_k| ≤ λ_0

> [9] W. Zhang, W. Ouyang, W. Li, and D. Xu. Collaborative and adversarial network for unsupervised domain adaptation. In CVPR, pages 3801–3809, 2018.

## Unsupervised DA method: MADA (2.3)

The difficulty of domain adaptation:

- target label space is only a subspace of the source label space.
- discriminative structures may be mixed up or falsely aligned across domains.

![](img/a04b187c89c5018c5ef6132980e27196_259_0.png)

> [10] Z. Pei, Z. Cao, M. Long, and J. Wang. Multi-adversarial domain adaptation. In AAAI Conference on Artificial Intelligence, 2018

min_θ 1/n Σ_{i=1}^n w_i L(x_i^s, y_i^s, θ)

A multi-adversarial domain adaptation (MADA) approach captures multimode structures enable fine-grained alignment of different data distributions based on multiple domain discriminators.

![](img/a04b187c89c5018c5ef6132980e27196_260_0.png)

It is a natural idea to use ŷ_i as the probability to indicate how much each data point x_i should be attended to the K domain discriminators G_d^k. The attention of each point x_i to a domain discriminator G_d^k can be modeled by weighting its features G_f(x_i) with probability ŷ_ik.

C(θ_f, θ_y, {θ_d^k}_{k=1}^K) = 1/n_s Σ_{x_i∈D_s} L_y(G_y(G_f(x_i)), y_i) - λ/n Σ_{k=1}^K Σ_{x_i∈D} L_d^k(G_d^k(ŷ_i^k G_f(x_i)), d_i)

(θ̂_f, θ̂_y) = arg min_{θ_f, θ_y} C(θ_f, θ_y, {θ_d^k}_{k=1}^K), (θ̂_d^1, ..., θ̂_d^K) = arg max_{θ_d^1, ..., θ_d^K} C(θ_f, θ_y, {θ_d^k}_{k=1}^K)

**Table 1: Accuracy (%) on *Office-31* for unsupervised domain adaptation (AlexNet and ResNet)**

| Method | A → W | D → W | W → D | A → D | D → A | W → A | Avg |
|---|---:|---:|---:|---:|---:|---:|---:|
| AlexNet (Krizhevsky, Sutskever, and Hinton 2012) | 60.6±0.4 | 95.4±0.2 | 99.0±0.1 | 64.2±0.3 | 45.5±0.5 | 48.3±0.5 | 68.8 |
| TCA (Pan et al. 2011) | 59.0±0.0 | 90.2±0.0 | 88.2±0.0 | 57.8±0.0 | 51.6±0.0 | 47.9±0.0 | 65.8 |
| GFK (Gong et al. 2012) | 58.4±0.0 | 93.6±0.0 | 91.0±0.0 | 58.6±0.0 | 52.4±0.0 | 46.1±0.0 | 66.7 |
| DDC (Tzeng et al. 2014) | 61.0±0.5 | 95.0±0.3 | 98.5±0.3 | 64.9±0.4 | 47.2±0.5 | 49.4±0.4 | 69.3 |
| DAN (Long et al. 2015) | 68.5±0.3 | 96.0±0.1 | 99.0±0.1 | 66.8±0.2 | 50.0±0.4 | 49.8±0.3 | 71.7 |
| RTN (Long et al. 2016) | 73.3±0.2 | 96.8±0.2 | 99.6±0.1 | 71.0±0.2 | 50.5±0.3 | 51.0±0.1 | 73.7 |
| RevGrad (Ganin and Lempitsky 2015) | 73.0±0.5 | 96.4±0.3 | 99.2±0.3 | 72.3±0.3 | 52.4±0.4 | 50.4±0.5 | 74.1 |
| **MADA** | **78.5±0.2** | **99.8±0.1** | **100.0±0.0** | **74.1±0.1** | **56.0±0.2** | **54.5±0.3** | **77.1** |
| ResNet (He et al. 2016) | 68.4±0.2 | 96.7±0.1 | 99.3±0.1 | 68.9±0.2 | 62.5±0.3 | 60.7±0.3 | 76.1 |
| TCA (Pan et al. 2011) | 74.7±0.0 | 96.7±0.0 | 99.6±0.0 | 76.1±0.0 | 63.7±0.0 | 62.9±0.0 | 79.3 |
| GFK (Gong et al. 2012) | 74.8±0.2 | 95.0±0.0 | 98.2±0.0 | 76.5±0.0 | 65.4±0.0 | 63.0±0.0 | 78.8 |
| DDC (Tzeng et al. 2014) | 75.8±0.2 | 95.0±0.2 | 98.2±0.1 | 77.5±0.3 | 67.4±0.4 | 64.0±0.5 | 79.7 |
| DAN (Long et al. 2015) | 83.8±0.4 | 96.8±0.2 | 99.5±0.1 | 78.4±0.2 | 66.7±0.3 | 62.7±0.2 | 81.3 |
| RTN (Long et al. 2016) | 84.5±0.2 | 96.8±0.1 | 99.4±0.1 | 77.5±0.3 | 66.2±0.2 | 64.8±0.3 | 81.6 |
| RevGrad (Ganin and Lempitsky 2015) | 82.0±0.4 | 96.9±0.2 | 99.1±0.1 | 79.7±0.4 | 68.2±0.4 | **67.4±0.5** | 82.2 |
| **MADA** | **90.0±0.1** | **97.4±0.1** | **99.6±0.1** | **87.8±0.2** | **70.3±0.3** | 66.4±0.3 | **85.2** |

**Table 3: Accuracy (%) on *Office-31* for domain adaptation from 31 classes to 25 classes (AlexNet)**

| Method | A → W | D → W | W → D | A → D | D → A | W → A | Avg |
|---|---:|---:|---:|---:|---:|---:|---:|
| AlexNet (Krizhevsky, Sutskever, and Hinton 2012) | 58.2±0.4 | 95.9±0.2 | 99.0±0.1 | 60.4±0.3 | 49.8±0.5 | 47.3±0.5 | 68.4 |
| RevGrad (Ganin and Lempitsky 2015) | 65.1±0.5 | 91.7±0.3 | 97.1±0.3 | 60.6±0.3 | 42.1±0.4 | 42.9±0.5 | 66.6 |
| **MADA** | **70.8±0.2** | **96.6±0.1** | **99.5±0.3** | **69.6±0.1** | **51.4±0.2** | **54.2±0.3** | **73.7** |
