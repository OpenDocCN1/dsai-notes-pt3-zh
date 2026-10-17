# # Upper Confidence Bounds on Trees (UCT)

+   • Applying this idea in an MCTS algorithm gives the Upper Confidence Bounds on Trees (UCT) algorithm due to Kocsis and Szepesvari [3], where Black's UCB score Z(s; a) of an action a in state s is obtained by as following

\(Z(s,a)=\frac{W(s,a)}{N(s,a)}+B(s,a),\)

\(B(s,a)=C\sqrt{\frac{\log N(s)}{N(s,a)}},\)

where \(C>0\) is a tuning constant, \(N(s,a)\) is the number of simulations in which move \(a\) was selected from state \(s\), \(W(s,a)\) is the total reward collected at terminal states during these simulations, \(N(s)=\sum_a N(s,a)\) is the number of simulations from state \(s\), and \(B(s,a)\) is the *exploration bonus*. Each move is scored by optimistically biasing the sample mean, by adding an exploration bonus. This bonus is largest for the actions that have been tried the least number of times, and are therefore the most uncertain. This encourages rarely explored moves to be tried more frequently.

[3]L. Kocsis and C. Szepesvari, Bandit based Monte-Carlo planning, In 15th European Conference on Machine Learning (ECML), 282-293, 2006.