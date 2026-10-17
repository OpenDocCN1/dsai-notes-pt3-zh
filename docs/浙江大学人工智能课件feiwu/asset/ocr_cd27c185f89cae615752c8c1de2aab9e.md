# # Depth-first search

+   - **Depth-first search (DFS)** always expands the deepest node in the current frontier of the search tree.

+   - The search proceeds immediately to the deepest level of the search tree, where the nodes have no successors.

+   - As those nodes are expanded, they are dropped from the frontier, so then the search “backs up” to the next deepest node that still has unexplored successors.

+   - **whereas breadth-first-search uses a FIFO queue, depth-first search uses a LIFO queue.**