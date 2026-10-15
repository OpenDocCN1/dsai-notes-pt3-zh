
## Why Not Semi-Supervised Clustering?

- Much information (in multiple relations) is needed to judge whether two tuples are similar
- A user may not be able to provide a good training set
- It is much easier for a user to specify an attribute as a hint, such as a student's *research area*

Tuples to be compared

User hint

![](img/6d25e92eb0bd56a22c311279c19b06b4_1373_0.png)

## CrossClus: An Overview

- Measure *similarity between features* by how they group objects into clusters
- Use a heuristic method to search for pertinent features
  - *Start from user-specified feature and gradually expand search range*
- Use *tuple ID propagation* to create feature values
  - Features can be easily created during the expansion of search range, by propagating IDs
- Explore three clustering algorithms: *k-means, k-medoids,* and hierarchical clustering

## Multi-Relational Features

- A multi-relational feature is defined by:
  - A join path, e.g., *Student → Register → OpenCourse → Course*
  - An attribute, e.g., *Course.area*
  - (For numerical feature) an aggregation operator, e.g., sum or average
- Categorical feature f = [*Student → Register → OpenCourse → Course*, *Course.area*, null]

areas of courses of each student

| Tuple | Areas of courses |  |  |
|---|---|---|---|
|  | *DB* | *AI* | *TH* |
| t₁ | 5 | 5 | 0 |
| t₂ | 0 | 3 | 7 |
| t₃ | 1 | 5 | 4 |
| t₄ | 5 | 0 | 5 |
| t₅ | 3 | 3 | 4 |

Values of feature f

| Tuple | Feature f |  |  |
|---|---|---|---|
|  | *DB* | *AI* | *TH* |
| t₁ | 0.5 | 0.5 | 0 |
| t₂ | 0 | 0.3 | 0.7 |
| t₃ | 0.1 | 0.5 | 0.4 |
| t₄ | 0.5 | 0 | 0.5 |
| t₅ | 0.3 | 0.3 | 0.4 |

f(t₁) f(t₂) f(t₃) f(t₄) f(t₅)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1375_0.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1375_1.png)

## Representing Features

- Similarity between tuples $t_1$ and $t_2$ w.r.t. categorical feature $f$
- — Cosine similarity between vectors $f(t_1)$ and $f(t_2)$

```
sim_f(t_1,t_2)= \frac{\sum_{k=1}^{L} f(t_1).p_k \cdot f(t_2).p_k}{\sqrt{\sum_{k=1}^{L} f(t_1).p_k^2} \cdot \sqrt{\sum_{k=1}^{L} f(t_2).p_k^2}}
```

![](img/6d25e92eb0bd56a22c311279c19b06b4_1376_0.png)

- Most important information of a feature $f$ is how $f$ groups tuples into clusters

- $f$ is represented by similarities between every pair of tuples indicated by $f$

- The horizontal axes are the tuple indices, and the vertical axis is the similarity

- This can be considered as a vector of $N \times N$ dimensions

## Similarity Between Features

### Values of Feature f and g

| | Feature f (course) | | Feature g (group) |
| | DB | AI | TH | | Info sys | Cog sci | Theory |
| t₁ | 0.5 | 0.5 | 0 | | 1 | 0 | 0 |
| t₂ | 0 | 0.3 | 0.7 | | 0 | 0 | 1 |
| t₃ | 0.1 | 0.5 | 0.4 | | 0 | 0.5 | 0.5 |
| t₄ | 0.5 | 0 | 0.5 | | 0.5 | 0 | 0.5 |
| t₅ | 0.3 | 0.3 | 0.4 | | 0.5 | 0.5 | 0 |

![](img/6d25e92eb0bd56a22c311279c19b06b4_1377_0.png)

Similarity between two features – cosine similarity of two vectors

```
sim(f, g) = (V^f · V^g) / (|V^f| |V^g|)
```

![](img/6d25e92eb0bd56a22c311279c19b06b4_1377_1.png)

## Computing Feature Similarity

Feature f
DB
AI
TH
Tuples
Feature g
Info sys
Cog sci
Theory

Similarity between feature values w.r.t. the tuples
sim(f_k, g_q) = Σ_{i=1 to N} f(t_i)·p_k · g(t_i)·p_q

DB
Info sys

V^f · V^g = Σ_{i=1}^N Σ_{j=1}^N sim_g(t_i, t_j)
Tuple similarities, hard to compute

m_g(t_i, t_j) = Σ_{k=1}^l Σ_{q=1}^m ( ... )^2
Feature value similarities, easy to compute

DB
AI
TH
Info sys
Cog sci
Theory

Compute similarity between each pair of feature values by one scan on data

## Searching for Pertinent Features

Different features convey different aspects of information

![](img/6d25e92eb0bd56a22c311279c19b06b4_1379_0.png)

- Features conveying same aspect of information usually cluster tuples in more similar ways
  - Research group areas vs. conferences of publications
- Given user specified feature
  - Find pertinent features by computing feature similarity
