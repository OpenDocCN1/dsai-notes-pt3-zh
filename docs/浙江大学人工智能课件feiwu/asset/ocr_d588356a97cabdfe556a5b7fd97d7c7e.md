# # A* search: Minimizing the total estimated solution cost

The most widely known form of best-first search is called A** search (pronounced “A-star search”). It evaluates nodes by combining _g_(_n_), the cost to reach the node, and _h_(_n_), the cost to get from the node to the goal:

_f_(_n_) = _g_(_n_) + _h_(_n_) .

Since _g_(_n_) gives the path cost from the start node to node _n_, and _h_(_n_) is the estimated cost of the cheapest path from _n_ to the goal, we have

_f_(_n_) = estimated cost of the cheapest solution through _n_ .

Thus, if we are trying to find the cheapest solution, a reasonable thing to try first is the node with the lowest value of _g_(_n_) + _h_(_n_). It turns out that this strategy is more than just reasonable: provided that the heuristic function _h_(_n_) satisfies certain conditions, A** search is both complete and optimal. The algorithm is identical to UNIFORM-COST-SEARCH except that A** uses _g_ + _h_ instead of _g_.

![](bbox=[0.141, 0.672, 0.871, 0.953])