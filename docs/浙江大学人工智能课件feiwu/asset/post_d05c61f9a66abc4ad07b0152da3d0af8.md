

## Greedy best-first search

Figure 3.23 shows the progress of a greedy best-first search using _h<sub>SLD</sub>_ to find a path from Arad to Bucharest. The first node to be expanded from Arad will be Sibiu because it is closer to Bucharest than either Zerind or Timisoara. The next node to be expanded will be Fagaras because it is closest. Fagaras in turn generates Bucharest, which is the goal. For this particular problem, greedy best-first search using _h<sub>SLD</sub>_ finds a solution without ever expanding a node that is not on the solution path; hence, its search cost is minimal. It is not optimal, however: the path via Sibiu and Fagaras to Bucharest is 32 kilometers longer than the path through Rimnicu Vilcea and Pitesti. This shows why the algorithm is called “greedy”—at each step it tries to get as close to the goal as it can.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_794_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_794_1.png)

Greedy best-first search is both non-optimal and incomplete (such as leading to an infinite loop)

Greedy best-first tree search is also incomplete even in a finite state space, much like depth-first search. Consider the problem of getting from Iasi to Fagaras. The heuristic suggests that Neamt be expanded first because it is closest to Fagaras, but it is a dead end. The solution is to go first to Vaslui—a step that is actually farther from the goal according to the heuristic—and then to continue to Urziceni, Bucharest, and Fagaras. The algorithm will never find this solution, however, because expanding Neamt puts Iasi back into the frontier. Iasi is closer to Fagaras than Vaslui is, and so Iasi will be expanded again, leading to an infinite loop. (The graph search version is complete in finite spaces, but not in infinite ones.) The worst-case time and space complexity for the tree version is _O_(_b<sup>m</sup>_), where _m_ is the maximum depth of the search space. With a good heuristic function, however, the complexity can be reduced substantially. The amount of the reduction depends on the particular problem and on the quality of the heuristic.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_795_0.png)

## A* search: Minimizing the total estimated solution cost

The most widely known form of best-first search is called A* search (pronounced “A-star search”). It evaluates nodes by combining _g_(_n_), the cost to reach the node, and _h_(_n_), the cost to get from the node to the goal:

_f_(_n_) = _g_(_n_) + _h_(_n_) .

Since _g_(_n_) gives the path cost from the start node to node _n_, and _h_(_n_) is the estimated cost of the cheapest path from _n_ to the goal, we have

_f_(_n_) = estimated cost of the cheapest solution through _n_ .

Thus, if we are trying to find the cheapest solution, a reasonable thing to try first is the node with the lowest value of _g_(_n_) + _h_(_n_). It turns out that this strategy is more than just reasonable: provided that the heuristic function _h_(_n_) satisfies certain conditions, A* search is both complete and optimal. The algorithm is identical to UNIFORM-COST-SEARCH except that A* uses _g_ + _h_ instead of _g_.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_796_0.png)

### (a) The initial state

### (b) After expanding Arad

### (c) After expanding Sibiu

### (d) After expanding Rimnicu Vilea

Figure 3.24 Stages in an A* search for Bucharest. Nodes are labeled with _f_ = _g_ + _h_. The _h_ values are the straight-line distances to Bucharest taken from Figure 3.22.

Figure 3.2 A simplified road map of part of Romania.

Figure 3.22 Values of _h<sub>SLD</sub>_—straight-line distances to Bucharest.

| Arad    | 366   | Mehadia   | 241   |
|---------|-------|-----------|-------|
| Bucharest | 0   | Neamt   | 234   |
| Craiova   | 160   | Oradea   | 380   |
| Drobeta   | 242   | Pitesti   | 100   |
| Eforie   | 161   | Rimnicu Vilea | 193   |
| Fagaras   | 176   | Sibiu   | 253   |
| Giurgiu   | 77   | Timisoara   | 329   |
| Hirsova   | 151   | Urziceni   | 80   |
| Iasi    | 226   | Vaslui   | 199   |
| Lugoj   | 244   | Zerind   | 374   |

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_797_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_797_1.png)

