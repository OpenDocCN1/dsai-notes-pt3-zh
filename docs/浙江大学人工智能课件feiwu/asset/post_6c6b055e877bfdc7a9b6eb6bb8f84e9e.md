
## Properties of α-β

- The benefit of alpha–beta pruning lies in the fact that branches of the search tree can be eliminated. This way, the search time can be limited to the 'more promising' subtree, and a deeper search can be performed in the same time.

The effectiveness of alpha–beta pruning is highly dependent on the order in which the states are examined. For example, in Figure 5.5(e) and (f), we could not prune any successors of D at all because the worst successors (from the point of view of MIN) were generated first. If the third successor of D had been generated first, we would have been able to prune the other two. This suggests that it might be worthwhile to try to examine first the successors that are likely to be best.

If this can be done,² then it turns out that alpha–beta needs to examine only O(b^(m/2)) nodes to pick the best move, instead of O(b^m) for minimax. This means that the effective branching factor becomes √b instead of b—for chess, about 6 instead of 35. Put another way, alpha–beta can solve a tree roughly twice as deep as minimax in the same amount of time. If successors are examined in random order rather than best-first, the total number of nodes examined will be roughly O(b^(3m/4)) for moderate b. For chess, a fairly simple ordering function (such as trying captures first, then threats, then forward moves, and then backward moves) gets you to within about a factor of 2 of the best-case O(b^(m/2)) result.

- Pruning **does not** affect final result
- Good move ordering improves effectiveness of pruning
- With "perfect ordering," time complexity = O(b^(m/2))
  - → **doubles** depth of search

## Imperfect Real-time Decisions

- The minimax algorithm generates the entire game search space, whereas the alpha–beta algorithm allows us to prune large parts of it. However, alpha–beta still has to search all the way to terminal states for at least a portion of the search space. This depth is usually not practical, because moves must be made in a reasonable amount of time—typically a few minutes at most.

- We should cut off the search earlier and apply a heuristic evaluation function to states in the search, effectively turning nonterminal nodes into terminal leaves. In other words, the suggestion is to alter minimax or alpha–beta in two ways: replace the utility function by a heuristic evaluation function EVAL, which estimates the position’s utility, and replace the terminal test by a cutoff test that decides when to apply EVAL.

- That gives us the following for heuristic minimax for state s and maximum depth d:

```
H-MINIMAX(s,d) =
⎧ EVAL(s)                                 if CUTOFF-TEST(s,d)
⎨ max_{a∈Actions(s)} H-MINIMAX(RESULT(s,a),d+1)   if PLAYER(s)=MAX
⎩ min_{a∈Actions(s)} H-MINIMAX(RESULT(s,a),d+1)   if PLAYER(s)=MIN.
```

### Imperfect Real-time Decisions: Evaluation functions

An evaluation function returns an *estimate* of the expected utility of the game from a given position. How exactly do we design good evaluation functions?

- First, the evaluation function should order the terminal states in the same way as the true utility function: states that are wins must evaluate better than draws, which in turn must be better than losses. Otherwise, an agent using the evaluation function might err even if it can see ahead all the way to the end of the game.
- Second, the computation must not take too long! (The whole point is to search faster.)
- Third, for nonterminal states, the evaluation function should be strongly correlated with the actual chances of winning.

Most evaluation functions work by calculating various **features** of the state—for example, in chess, we would have features for the number of white pawns, black pawns, white queens, black queens, and so on. The features, taken together, define various *categories* or *equivalence classes* of states: the states in each category have the same values for all the features.

The evaluation function cannot know which states are which, but it can return a single value that reflects the proportion of states with each outcome. For example, suppose our experience suggests that 72% of the states encountered in the two-pawns vs. one-pawn category lead to a win (utility +1); 20% to a loss (0), and 8% to a draw (1/2). Then a reasonable evaluation for states in the category is the expected value: (0.72 × +1) + (0.20 × 0) + (0.08 × 1/2) = 0.76
