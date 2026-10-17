# # Our Agenda in Adversarial Search

+   - **Minimax Search**: How to compute an optimal strategy? Minimax is the canonical (and easiest to understand) algorithm for solving games, i.e., computing an optimal strategy.
+   - **Evaluation Functions**: But what if we don’t have the time/memory to solve the entire game? Given limited time, the best we can do is look ahead as far as we can. Evaluation functions tell us how to evaluate the leaf states at the cut-off.
+   - **Alpha-Beta Pruning Search**: How to prune unnecessary parts of the tree? An essential improvement over Minimax.
+   - **Monte-Carlo Tree Search (MCTS)**: An alternative form of game search, based on sampling rather than exhaustive enumeration. The main alternative to Alpha-Beta Search.

Alpha-Beta: state of the art in Chess  
MCTS: state of the art in Go