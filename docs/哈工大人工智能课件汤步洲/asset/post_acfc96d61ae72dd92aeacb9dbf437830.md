
## Probabilistic Models

- A probabilistic model is a joint distribution over a set of random variables
- Probabilistic models:
  - (Random) variables with domains
  - Assignments are called *outcomes*
  - Joint distributions: say whether assignments (outcomes) are likely
  - *Normalized*: sum to 1.0
  - Ideally: only certain variables directly interact
- Constraint satisfaction problems:
  - Variables with domains
  - Constraints: state whether assignments are possible
  - Ideally: only certain variables directly interact

## Distribution over T,W

| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |

## Constraint over T,W

| T | W | P |
|---|---|---|
| hot | sun | T |
| hot | rain | F |
| cold | sun | F |
| cold | rain | T |

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_547_0.png)

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_547_1.png)

## Events

- An *event* is a set E of outcomes

  $P(E) = \sum_{(x_1...x_n)\in E} P(x_1...x_n)$
- From a joint distribution, we can calculate the probability of any event
  - Probability that it's hot AND sunny?
  - Probability that it's hot?
  - Probability that it's hot OR sunny?
- Typically, the events we care about are *partial assignments*, like P(T=hot)

P(T, W)

| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |

## Quiz: Events

- P(+x, +y) ?
- P(+x) ?
- P(-y OR +x) ?

P(X, Y)

| X | Y | P |
|---|---|---|
| +x | +y | 0.2 |
| +x | -y | 0.3 |
| -x | +y | 0.4 |
| -x | -y | 0.1 |

## Marginal Distributions

- Marginal distributions are sub-tables which eliminate variables
- Marginalization (summing out): Combine collapsed rows by adding

P(T, W)
| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |

P(t) = Σ_s P(t, s)

P(T)
| T | P |
|---|---|
| hot | 0.5 |
| cold | 0.5 |

P(s) = Σ_t P(t, s)

P(W)
| W | P |
|---|---|
| sun | 0.6 |
| rain | 0.4 |

P(X₁ = x₁) = Σ_{x₂} P(X₁ = x₁, X₂ = x₂)

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_550_0.png)

## Quiz: Marginal Distributions

| P(X, Y) |
|---|---|---|
| X | Y | P |
| +x | +y | 0.2 |
| +x | -y | 0.3 |
| -x | +y | 0.4 |
| -x | -y | 0.1 |

P(x) = Σ_y P(x, y)

P(y) = Σ_x P(x, y)

| P(X) |
|---|---|
| X | P |
| +x | 0.5 |
| -x | 0.5 |

| P(Y) |
|---|---|
| Y | P |
| +y | 0.6 |
| -y | 0.4 |

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_551_0.png)

## Conditional Probabilities

- A simple relation between joint and conditional probabilities
  - In fact, this is taken as the *definition* of a conditional probability

```
P(a|b) = P(a, b) / P(b)
```

![](img/9a6adc64cdb7c98bcd042d4d38c7b00d_552_0.png)

# P(T, W)

| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |

```
P(W = s | T = c) = P(W = s, T = c) / P(T = c) = 0.2 / 0.5 = 0.4
```

```
= P(W = s, T = c) + P(W = r, T = c)
= 0.2 + 0.3 = 0.5
```

## Quiz: Conditional Probabilities

• P(+x | +y) ?

P(X,Y)

| X | Y | P |
| --- | --- | --- |
| +x | +y | 0.2 |
| +x | -y | 0.3 |
| -x | +y | 0.4 |
| -x | -y | 0.1 |

• P(-x | +y) ?

• P(-y | +x) ?

## Conditional Distributions

- Conditional distributions are probability distributions over some variables given fixed values of others

Conditional Distributions

P(W|T)

P(W|T = hot)

| W | P |
|---|---|
| sun | 0.8 |
| rain | 0.2 |

P(W|T = cold)

| W | P |
|---|---|
| sun | 0.4 |
| rain | 0.6 |

Joint Distribution

P(T, W)

| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |

## Normalization Trick

P(T, W)

| T | W | P |
|---|---|---|
| hot | sun | 0.4 |
| hot | rain | 0.1 |
| cold | sun | 0.2 |
| cold | rain | 0.3 |

P(W = s | T = c) = P(W = s, T = c) / P(T = c) = P(W = s, T = c) / [P(W = s, T = c) + P(W = r, T = c)] = 0.2 / (0.2 + 0.3) = 0.4

P(W = r | T = c) = P(W = r, T = c) / P(T = c) = P(W = r, T = c) / [P(W = s, T = c) + P(W = r, T = c)] = 0.3 / (0.2 + 0.3) = 0.6

P(W | T = c)

| W | P |
|---|---|
| sun | 0.4 |
| rain | 0.6 |
