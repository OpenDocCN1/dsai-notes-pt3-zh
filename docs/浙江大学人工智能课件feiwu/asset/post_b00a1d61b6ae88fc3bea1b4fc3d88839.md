
## Depth-first search

```
generalSearch(problem, stack)
# of nodes tested: 6, expanded: 5
```

| Expanded node | Nodes list |
|---|---|
|  | {S} |
| S | {A,B,C} |
| A | {D,E,B,C} |
| D | {H,E,B,C} |
| H | {E,B,C} |
| E | {G,B,C} |
| G | {B,C} |

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_787_0.png)

*Dive into the search tree as far as you can, backing up only when there is no way to proceed*

```
function Depth-First-Search(problem) returns solution
    nodes := Make-Queue(Make-Node(Initial-State(problem)))
    loop do
        if nodes is empty then return failure
        node := Remove-Front(nodes)
        if Goal-Test[problem] applied to State(node) succeeds
            then return node
        new-nodes := Expand(node, Operators[problem])
        nodes := Insert-At-Front-of-Queue(new-nodes)
    end
```

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_789_0.png)

### Properties of depth-first search

- **Completeness:** No, fails in infinite state-space
- **Time complexity:** $O(b^m)$
- **Space complexity:** $O(bm)$
- **Optimality:** No – it may never find the path!

The time complexity of depth-first graph search is bounded by the size of the state space (which may be infinite, of course). A depth-first tree search, on the other hand, may generate all of the $O(b^m)$ nodes in the search tree, where $m$ is the maximum depth of any node; this can be much greater than the size of the state space. Note that $m$ itself can be much larger than $d$ (the depth of the shallowest solution) and is infinite if the tree is unbounded.

Ensure that the nodes that are visited are marked. This will prevent you from visiting the same node more than once. If you do not mark the nodes that are visited and you visit the same node more than once, you may end up in an infinite loop.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_790_0.png)

Visit nodes in the order A, B, D, F, E, A, B, D, F, E, etc. forever, caught in the A, B, D, F, E cycle and never reaching C or G.

## Comparing uninformed search strategies

Figure 3.21 compares search strategies in terms of the four evaluation criteria set forth in Section 3.3.2. This comparison is for tree-search versions. For graph searches, the main differences are that depth-first search is complete for finite state spaces and that the space and time complexities are bounded by the size of the state space.

| Criterion | Breadth-First | Uniform-Cost | Depth-First | Depth-Limited | Iterative Deepening | Bidirectional (if applicable) |
|---|---|---|---|---|---|---|
| Complete? | Yes<sup>a</sup> | Yes<sup>a,b</sup> | No | No | Yes<sup>a</sup> | Yes<sup>a,d</sup> |
| Time | $O(b^d)$ | $O(b^{1+\lfloor C^*/\varepsilon \rfloor})$ | $O(b^m)$ | $O(b^l)$ | $O(b^d)$ | $O(b^{d/2})$ |
| Space | $O(b^d)$ | $O(b^{1+\lfloor C^*/\varepsilon \rfloor})$ | $O(bm)$ | $O(bl)$ | $O(bd)$ | $O(b^{d/2})$ |
| Optimal? | Yes<sup>c</sup> | Yes | No | No | Yes<sup>c</sup> | Yes<sup>c,d</sup> |

**Figure 3.21** Evaluation of tree-search strategies. *b* is the branching factor; *d* is the depth of the shallowest solution; *m* is the maximum depth of the search tree; *l* is the depth limit. Superscript caveats are as follows: <sup>a</sup> complete if *b* is finite; <sup>b</sup> complete if step costs ≥ ε for positive ε; <sup>c</sup> optimal if step costs are all identical; <sup>d</sup> if both directions use breadth-first search.

## Informed (Heuristic) Search Strategies

How an informed search strategy—one that uses problem-specific knowledge beyond the definition of the problem itself—can find solutions more efficiently than can an uninformed strategy.

- Greedy best-first search
- A* search: Minimizing the total estimated solution cost

The general approach we consider is called best-first search. Best-first search is an instance of the general TREE-SEARCH or GRAPH-SEARCH algorithm in which a node is selected for expansion based on an evaluation function, f(n). The evaluation function is construed as a cost estimate, so the node with the lowest evaluation is expanded first. The implementation of best-first graph search is identical to that for uniform-cost search (Figure 3.14), except for the use of f instead of g to order the priority queue.

The choice of f determines the search strategy. (For example, as Exercise 3.21 shows, best-first tree search includes depth-first search as a special case.) Most best-first algorithms include as a component of f a heuristic function, denoted h(n):

h(n) = estimated cost of the cheapest path from the state at node n to a goal state.

(Notice that h(n) takes a node as input, but, unlike g(n), it depends only on the state at that node.) For example, in Romania, one might estimate the cost of the cheapest path from Arad to Bucharest via the straight-line distance from Arad to Bucharest.
