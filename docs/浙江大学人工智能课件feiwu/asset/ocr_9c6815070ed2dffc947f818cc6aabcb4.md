# # Application of RNN

# ## Bidirectional RNNs

![](bbox=[0.141, 0.299, 0.422, 0.953])

Figure 10.11: Computation of a typical bidirectional recurrent neural network, meant to learn to map input sequences _x_ to target sequences _y_, with loss _L_<sup>(_t_)</sup> at each step _t_. The _h_ recurrence propagates information forward in time (towards the right) while the _g_ recurrence propagates information backward in time (towards the left). Thus at each point _t_, the output units _o_<sup>(_t_)</sup> can benefit from a relevant summary of the past in its _h_<sup>(_t_)</sup> input and from a relevant summary of the future in its _g_<sup>(_t_)</sup> input.