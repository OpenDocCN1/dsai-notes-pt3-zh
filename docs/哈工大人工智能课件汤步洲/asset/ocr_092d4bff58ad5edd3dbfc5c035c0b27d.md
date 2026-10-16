# Evidence II

+   - We eliminate all vars (T) other than query + evidence

$P(+r)$

| +r | 0.1 |

$P(T\mid +r)$

| +r | +t | 0.8 |
|---|---|---|
| +r | -t | 0.2 |

$P(L\mid T)$

| +t | +l | 0.3 |
|---|---|---|
| +t | -l | 0.7 |
| -t | +l | 0.1 |
| -t | -l | 0.9 |

Join T

$P(T,L\mid +r)$

| +r | +t | +l | 0.24 |
|---|---|---|---|
| +r | +t | -l | 0.56 |
| +r | -t | +l | 0.02 |
| +r | -t | -l | 0.18 |

Sum out T

$P(L\mid +r)$

| +r | +l | 0.26 |
|---|---|---|
| +r | -l | 0.74 |