# # AlphaGo

Aided by the useful information learned by two deep convolutional neural networks (a.k.a., deep learning), policy network and value network, Google’s AlphaGo applies MCTS in an innovative way.

+   • First, for the tree policy to select child, instead of using the UCB method, AlphaGo takes into account the prior probability of actions learned by the policy network. More specifically, for node _v_<sub>0</sub>, the child _v_ is selected by maximizing

```
\(\frac{Q(v)}{N(v)} + \frac{P(v|v_0)}{1 + N(v)},\)
(2)
```

where _P_(_v_|_v_<sub>0</sub>) is the prior probability that is provided by the policy network. This greatly improves the child selection policy, and thus grants more professional moves (e.g., by human experts) priorities in MCTS simulation.

+   • Second, for the default policy to evaluate expanded nodes, AlphaGo combines the outcomes from simulation steps and node values learned by the value network, and their weights are balanced by a constant \(\lambda\).

Note that both the policy network and value network are trained offline, which greatly reduces the time cost in a real-time contest.