# # Maximum likelihood and least squares

As before, we assume that the target variable _t_ is given by a deterministic function _y_(**x**, **w**) with additive Gaussian noise so that

\(t=y(\mathbf{x}, \mathbf{w})+\epsilon\) (3.7)

where \(\epsilon\) is a zero mean Gaussian random variable with precision (inverse variance) \(\beta\). Thus we can write

\(p(t|\mathbf{x}, \mathbf{w}, \beta)=\mathcal{N}(t|y(\mathbf{x}, \mathbf{w}), \beta^{-1}).\) (3.8)

Recall that, if we assume a squared loss function, then the optimal prediction, for a new value of **x**, will be given by the conditional mean of the target variable. In the case of a Gaussian conditional distribution of the form (3.8), the conditional mean will be simply

\(\mathbb{E}[t|\mathbf{x}]=\int tp(t|\mathbf{x})\mathrm{d}t=y(\mathbf{x}, \mathbf{w}).\) (3.9)

Note that the Gaussian noise assumption implies that the conditional distribution of _t_ given **x** is unimodal, which may be inappropriate for some applications. An extension to mixtures of conditional Gaussian distributions, which permit multimodal conditional distributions, will be discussed in Section 14.5.1.