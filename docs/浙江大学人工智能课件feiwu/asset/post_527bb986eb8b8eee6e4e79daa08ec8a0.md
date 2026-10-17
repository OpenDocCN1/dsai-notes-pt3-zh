

## Iterative deepening depth-first search

### Iterative deepening search (IDS)

```
function ITERATIVE-DEEPENING-SEARCH(problem) returns a solution, or failure
  for depth = 0 to ∞ do
    result ← DEPTH-LIMITED-SEARCH(problem, depth)
    if result ≠ cutoff then return result
```

**Figure 3.18** The iterative deepening search algorithm, which repeatedly applies depth-limited search with increasing limits. It terminates when a solution is found or if the depth-limited search returns failure, meaning that no solution exists.

- the total number of nodes generated in the worst case is:
  - N(IDS) = (d)b + (d − 1)b² + ⋯ + (1)bᵈ

- E.g. b=10, d=5
  - N(IDS) = 50 + 400 + 3,000 + 20,000 + 100,000 = 123,450
  - N(BFS) = 10 + 100 + 1,000 + 10,000 + 100,000 = 111,110

• Iterativ

Limit = 0

Limit = 1

Limit = 2

Limit = 3

Figure 3.19 Four iterations of iterative deepening search on a binary tree.

## Comparing uninformed search strategies

Figure 3.21 compares search strategies in terms of the four evaluation criteria set forth in Section 3.3.2. This comparison is for tree-search versions. For graph searches, the main differences are that depth-first search is complete for finite state spaces and that the space and time complexities are bounded by the size of the state space.

| Criterion | Breadth-First | Uniform-Cost | Depth-First | Depth-Limited | Iterative Deepening | Bidirectional (if applicable) |
|---|---|---|---|---|---|---|
| Complete? | Yesᵃ | Yesᵃ,ᵇ | No | No | Yesᵃ | Yesᵃ,ᵈ |
| Time | O(bᵈ) | O(b^{1+⌊C*/ε⌋}) | O(bᵐ) | O(bˡ) | O(bᵈ) | O(b^{d/2}) |
| Space | O(bᵈ) | O(b^{1+⌊C*/ε⌋}) | O(bm) | O(bl) | O(bᵈ) | O(b^{d/2}) |
| Optimal? | Yesᶜ | Yes | No | No | Yesᶜ | Yesᶜ,ᵈ |

**Figure 3.21** Evaluation of tree-search strategies. *b* is the branching factor; *d* is the depth of the shallowest solution; *m* is the maximum depth of the search tree; *l* is the depth limit. Superscript caveats are as follows: ᵃ complete if *b* is finite; ᵇ complete if step costs ≥ ε for some positive ε; ᶜ optimal if step costs are all identical; ᵈ if both directions use breadth-first search.

## Informed (Heuristic) Search Strategies

- How an informed search strategy—one that uses problem-specific knowledge beyond the definition of the problem itself—can find solutions more efficiently than can an uninformed strategy.
  - Greedy best-first search
  - A* search: Minimizing the total estimated solution cost

- First, let’s consider a general approach which is called **best-first search**

## Informed (Heuristic) Search Strategies

- **Best-first search**
  - Best-first search is an instance of the general TREE-SEARCH or GRAPH-SEARCH algorithm in which a node is selected for expansion based on an **evaluation function**, _f_(_n_).
  - The evaluation function is construed as a cost estimate, so the node with the lowest evaluation is expanded first.
  - The implementation of best-first graph search is identical to that for uniform-cost search (Figure 3.14), except for the use of _f_ instead of _g_ to order the priority queue.
  - The choice of _f_ determines the search strategy.

## Informed (Heuristic) Search Strategies

- How to choose a **evaluation function** _f_ ?

- Most best-first algorithms include as a component of _f_ a **heuristic function**, denoted _h_(_n_): **estimated cost of the cheapest path from the state at node** _n_ **to a goal state**.

- _(Notice that h_(_n_) _takes a node as input, but, unlike g_(_n_)_, it depends only on the state at that node.)_ For example, in Romania, one might estimate the cost of the cheapest path from Arad to Bucharest via the **straight-line distance** from Arad to Bucharest.

- Heuristic functions are the most common form in which additional knowledge of the problem is imparted to the search algorithm.

- For now, we consider _h_(_n_) to be **arbitrary**, **nonnegative**, **problem-specific** functions, with one constraint: if _n_ is a goal node, then _h_(_n_)=0.

- **Greedy best-first search**: _f_(_n_) = _h_(_n_)

