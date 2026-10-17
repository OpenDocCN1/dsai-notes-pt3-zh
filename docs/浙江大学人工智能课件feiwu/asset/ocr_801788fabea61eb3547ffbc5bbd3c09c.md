# # K-means clustering

+   • Distortion measure (responsibilities):

\(J = \sum_{n=1}^N \sum_{k=1}^K r_{nk} \| \mathbf{x}_n - \boldsymbol{\mu}_k \|^2\)

\(\frac{\partial J}{\partial \boldsymbol{\mu}_k} = 2 \sum_{n=1}^N r_{nk} (\mathbf{x}_n - \boldsymbol{\mu}_k) = 0\)

\(\boldsymbol{\mu}_k = \frac{\sum_n r_{nk} \mathbf{x}_n}{\sum_n r_{nk}}\)

+   Responsibilities

+   Data

+   Prototypes (expected value )

\(r_{nk} = \left\{ \begin{array}{ll} 1 & \text{if } k = \text{arg min}_j \| \mathbf{x}_n - \boldsymbol{\mu}_j \|^2 \\ 0 & \text{otherwise.} \end{array} \right.\)

\(r_{n,k} = \left( \begin{array}{ c c c } 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{array} \text{Example: 5 data points and 3 clusters} \right)\)

# ## K-means algorithm (batch version):

+   1. Pick number of clusters \(k\)

+   2. Randomly scatter \(k\) “cluster centers” in data space

+   3. Repeat:

+   a. Assign each data point to its closest cluster center

+   b. Move each cluster center to the mean of the points assigned to it