# # Summary

Informed search methods may have access to a heuristic function h(n) that estimates
the cost of a solution from n.

+   - The generic best-first search algorithm selects a node for expansion according to
+   an evaluation function.

+   - Greedy best-first search expands nodes with minimal h(n). It is not optimal but
+   is often efficient.

+   - A* search expands nodes with minimal f(n) = g(n) + h(n). A* is complete and
+   optimal, provided that h(n) is admissible (for TREE-SEARCH) or consistent (for
+   GRAPH-SEARCH). The space complexity of A* is still prohibitive.

+   - RBFS (recursive best-first search) and SMA* (simplified memory-bounded A*)
+   are robust, optimal search algorithms that use limited amounts of memory; given
+   enough time, they can solve problems that A* cannot solve because it runs out of
+   memory.

+   - The performance of heuristic search algorithms depends on the quality of the heuristic
+   function. One can sometimes construct good heuristics by relaxing the problem definition,
+   by storing precomputed solution costs for subproblems in a pattern database, or
+   by learning from experience with the problem class.