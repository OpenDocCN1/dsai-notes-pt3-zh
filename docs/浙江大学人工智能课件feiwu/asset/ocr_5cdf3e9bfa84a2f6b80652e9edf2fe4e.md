# RNN Variants

# Other RNN Variants

**GRU** [*Learning phrase representations using rnn encoder-decoder for statistical machine translation*, Cho et al., 2014]

```
$$r_t = \sigma(W_{xr}x_t + W_{hr}h_{t-1} + b_r)$$

$$z_t = \sigma(W_{xz}x_t + W_{hz}h_{t-1} + b_z)$$

$$\tilde{h}_t = \tanh(W_{xh}x_t + W_{hh}(r_t \odot h_{t-1}) + b_h)$$

$$h_t = z_t \odot h_{t-1} + (1-z_t) \odot \tilde{h}_t$$
```

*The main difference with the LSTM is that a single gating unit simultaneously controls the forgetting factor and the decision to update the state unit.*

> [*LSTM: A Search Space Odyssey*, Greff et al., 2015]

[*An Empirical Exploration of Recurrent Network Architectures*, Jozefowicz et al., 2015]

```
**MUT1:**

$$z = \sigma(W_{xz}x_t + b_z)$$
$$r = \sigma(W_{xr}x_t + W_{hr}h_t + b_r)$$
$$h_{t+1} = \tanh(W_{hh}(r \odot h_t) + \tanh(x_t) + b_h) \odot z + h_t \odot (1-z)$$

**MUT2:**

$$z = \sigma(W_{xz}x_t + W_{hz}h_t + b_z)$$
$$r = \sigma(x_t + W_{hr}h_t + b_r)$$
$$h_{t+1} = \tanh(W_{hh}(r \odot h_t) + W_{xh}x_t + b_h) \odot z + h_t \odot (1-z)$$

**MUT3:**

$$z = \sigma(W_{xz}x_t + W_{hz}\tanh(h_t) + b_z)$$
$$r = \sigma(W_{xr}x_t + W_{hr}h_t + b_r)$$
$$h_{t+1} = \tanh(W_{hh}(r \odot h_t) + W_{xh}x_t + b_h) \odot z + h_t \odot (1-z)$$
```