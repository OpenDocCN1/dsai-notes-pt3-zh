

## The Bias-Variance Decomposition

Graphical illustration of bias and variance

We have: \(\mathbb{E}[L] = \iint L(t, y(x))p(x, t) \, dx \, dt = \iint \{y(x) - t\}^2 p(x, t) \, dx \, dt\)

\(\{y(x) - t\}^2 = \{y(x) - \mathbb{E}[t|x] + \mathbb{E}[t|x] - t\}^2\)

\(= \{y(x) - \mathbb{E}[t|x]\}^2 + 2\{y(x) - \mathbb{E}[t|x]\}\{\mathbb{E}[t|x] - t\} + \{\mathbb{E}[t|x] - t\}^2\)

\(\Rightarrow \mathbb{E}[L] = \int \{y(x) - \mathbb{E}[t|x]\}^2 p(x) \, dx + \int \{\mathbb{E}[t|x] - t\}^2 p(x) \, dx\)

Let : \(h(x) = \mathbb{E}[t|x] = \int t p(t|x) \, dt\)

\(\Rightarrow \mathbb{E}[L] = \int \{y(x) - h(x)\}^2 p(x) \, dx + \int \{h(x) - t\}^2 p(x, t) \, dx \, dt\)

For data set \(\mathcal{D}\): \(\{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] + \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}^2\)

\(= \{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})]\}^2 + \{\mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}^2\)

\(+2\{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})]\}\{\mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}\)

\(\Rightarrow \mathbb{E}_\mathcal{D} \left[ \{y(x; \mathcal{D}) - h(x)\}^2 \right]\)

\(= \underbrace{\{\mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}^2}_{(\text{bias})^2} + \underbrace{\mathbb{E}_\mathcal{D} \left[ \{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})]\}^2 \right]}_{\text{variance}}\)

## The Bias-Variance Trade-off

Substitute \(\mathbb{E}_D[(y(x;D)-h(x))^2]\)

Into: \(\mathbb{E}[L]=\int \{y(x)-h(x)\}^2p(x)\,dx+\int \{h(x)-t\}^2p(x,t)\,dx\,dt\)

Obtain: expected loss = \((\text{bias})^2+\text{variance}+\text{noise}\)

\(\mathbb{E}[L]=\int \{\mathbb{E}_D[y(x;D)]-h(x)\}^2p(x)\,dx+\int \mathbb{E}_D[\{y(x;D)-\mathbb{E}_D[y(x;D)]\}^2]p(x)\,dx+\int \{h(x)-t\}^2p(x,t)\,dx\,dt\)

bias²

variance

noise

Bias and variance contributing to total error

## Statistical Learning and Modeling
### LINEAR MODEL FOR CLASSIFICATION

References:
1. Bishop. “Pattern Recognition and Machine Learning”, Chapter 4. 2006.

## Basic Concepts

## Linearly separable

- Decision regions:
  - Input space is divided into several regions
- Decision boundaries (surfaces):
  - Under linear models, it's a linear function of the input vector x
  - (D-1)-dimensional hyper-plane within the D-dimensional input space
- Data sets whose classes can be separated exactly by linear decision surfaces are said to be *linear separable*.

## Representation of Class Labels

- Two classes (K=2):
  - Target variable t ∈ {0, 1}, t=1 represents class C₁, else class C₂
- K-classes (K>2):
  - 1-of-K coding scheme: t = (0, 1, 0, 0, 0)ᵀ
- Predict discrete class labels:
  - Linear model prediction (linear discriminant function): y(x) = wᵀx + w₀
  - Nonlinear function f(.) : R → (0, 1)
  - Generalized linear models:
    - f(.) : activation function
    - f⁻¹(.) : link function
    - y(x) = f(wᵀx + w₀)
  - Decision surface:
    - y(x) = constant → wᵀx + w₀ = constant

## Three classification approaches

- Discriminant function:

- Use discriminant functions directly, and do not compute probabilities

Given discriminant functions \( f_1(\mathbf{x}), \dots, f_K(\mathbf{x}) \)
Classify \(\mathbf{x}\) as class \( C_k \), **iff** \( f_k(\mathbf{x}) > f_j(\mathbf{x}), \forall j \neq k \)

- **Least-squares approach**: making the model predictions as close as possible to a set of target values

- **Fisher’s linear discriminant**: maximum class separation in the output space

- **The perceptron algorithm of Rosenblatt**: generalized linear model

