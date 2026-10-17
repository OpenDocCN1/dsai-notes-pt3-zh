# Properties of depth-first search

+   - **Completeness:** No, fails in infinite state-space
+   - **Time complexity:** $O(b^m)$
+   - **Space complexity:** $O(bm)$
+   - **Optimality:** No – it may never find the path!

The time complexity of depth-first graph search is bounded by the size of the state space (which may be infinite, of course). A depth-first tree search, on the other hand, may generate all of the $O(b^m)$ nodes in the search tree, where $m$ is the maximum depth of any node; this can be much greater than the size of the state space. Note that $m$ itself can be much larger than $d$ (the depth of the shallowest solution) and is infinite if the tree is unbounded.

ensure that the nodes that are visited are marked. This will prevent you from visiting the same node more than once. If you do not mark the nodes that are visited and you visit the same node more than once, you may end up in an infinite loop.

![](bbox=[0.598, 0.632, 0.821, 0.851])

visit nodes in the order A, B, D, F, E, A, B, D, F, E, etc. forever, caught in the A, B, D, F, E cycle and never reaching C or G.