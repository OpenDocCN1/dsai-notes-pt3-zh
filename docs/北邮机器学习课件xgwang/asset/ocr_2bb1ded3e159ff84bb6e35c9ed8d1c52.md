# Long Short-Term Memory (LSTM) net

f_t = σ(W_fx x_t + W_fh h_{t-1} + b_f), i_t = σ(W_ix x_t + W_ih h_{t-1} + b_i),
 o_t = σ(W_ox x_t + W_oh h_{t-1} + b_o)
 g_t = tanh(W_gx x_t + W_gh h_{t-1} + b_g), c_t = f_t ⊙ c_{t-1} + i_t ⊙ g_t
 h_t = o_t ⊙ tanh(c_t), z_t = softmax(W_z h_t + b_z)

![](bbox=[0.25, 0.48, 0.85, 0.88])