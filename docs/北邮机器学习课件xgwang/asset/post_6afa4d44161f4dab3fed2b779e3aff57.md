
## What is transfer learning?

Given a source domain $D_S$ and learning task $T_S$, a target domain $D_T$ and learning task $T_T$, transfer learning aims to help improve the learning of the target predictive function $f_T(\cdot)$ in $D_T$ using the knowledge in $D_S$ and $T_S$, where $D_S \neq D_T$, or $T_S \neq T_T$.

![](img/a04b187c89c5018c5ef6132980e27196_236_0.png)

## What is domain adaptation?

- **Domain adaptation:**
  - Source domain: abundant amount of labeled data.
  - Target domain: few or no labeled data.
  - Same tasks, but different data distribution.

![](img/a04b187c89c5018c5ef6132980e27196_237_0.png)

> [1] Pan S J, Yang Q. A survey on transfer learning[J]. IEEE Transactions on knowledge and data engineering, 2010, 22(10): 1345-1359.

## What is domain adaptation?

Due to many factors (e.g., illumination, pose, and image quality), there is always a **distribution change or domain shift** between two domains that can degrade the performance.

![](img/a04b187c89c5018c5ef6132980e27196_238_0.png)

[2] M. Wang and W. Deng. *Deep visual domain adaptation: A survey*. Neurocomputing, 312:135–153, 2018.

## What is domain adaptation?

Due to distribution change or domain shift between two domains, the classifier learned for the source domain can not be applied to the target domain.

![](img/a04b187c89c5018c5ef6132980e27196_239_0.png)

### SVHN→MNIST

![](img/a04b187c89c5018c5ef6132980e27196_239_1.png)

(a) non-adapted

### SVHN→MNIST

![](img/a04b187c89c5018c5ef6132980e27196_239_2.png)

(a) adapted

## What is domain adaptation?

- **Supervised DA**, a small amount of labeled target data are present. However, the labeled data are commonly not sufficient for tasks.
- **Semi-supervised DA**, both limited labeled data and redundant unlabeled data in the target domain are available in the training stage, which allows the networks to learn the structure information of the target domain.
- **Unsupervised DA**, no labeled but sufficient unlabeled target domain data are observable when training the network.

![](img/a04b187c89c5018c5ef6132980e27196_240_0.png)

## The key of transfer learning

The key element of transfer learning is to discover the commonness between the two fields. Once this commonness is discovered, transfer learning becomes easy. We call this commonness as common features in machine learning.

![](img/a04b187c89c5018c5ef6132980e27196_241_0.png)

VS

![](img/a04b187c89c5018c5ef6132980e27196_241_1.png)

![](img/a04b187c89c5018c5ef6132980e27196_241_2.png)

## Shallow domain adaptation

- **Traditional deep learning**
  
  min 1/n Σ_{i=1}^n L(x_i, y_i, θ)
- **Feature adaptation**
  
  min 1/n Σ_{i=1}^n L(φ(x_i^s), y_i^s, θ)
- **Instance adaptation**
  
  min 1/n Σ_{i=1}^n w_i L(x_i^s, y_i^s, θ)
- **Model adaptation**
  
  min 1/n Σ_{i=1}^n L(x_i^s, y_i^s, θ)

Slide credit: Meina Kan

> [1] Pan S J, Yang Q. A survey on transfer learning[J]. IEEE Transactions on knowledge and data engineering, 2010, 22(10): 1345-1359.

## Deep visual domain adaptation: A survey

fine-tuning the deep network with labeled or unlabeled target data to diminish the domain shift

using domain discriminators to encourage domain confusion through an adversarial objective

using the data reconstruction as an auxiliary task to ensure feature invariance

### Discrepancy-based DA

### Adversarial-based DA

### Reconstruction-based DA

- class criterion
- architecture criterion
- statistic criterion
- geometric criterion

- generative models
- non-generative models

- encoder-decoder reconstruction
- adversarial reconstruction

![](img/a04b187c89c5018c5ef6132980e27196_243_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_243_1.png)

![](img/a04b187c89c5018c5ef6132980e27196_243_2.png)

![](img/a04b187c89c5018c5ef6132980e27196_243_3.png)

## Supervised DA method: fine-tune

It showed how transferability is negatively affected by two distinct issues: optimization difficulties related to splitting networks in the middle of fragiley co-adapted layers and the specialization of higher layer features to the original task at the expense of performance on the target task.

|  | The size of target dataset |  |  |
|  | Low | Medium | High |
| The distance between domains | Low | Freeze | freeze or tune | Tune |
|  | Medium | freeze or tune | Tune | Tune |
|  | High | freeze or tune | Tune | Tune |

![](img/a04b187c89c5018c5ef6132980e27196_245_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_245_1.png)
