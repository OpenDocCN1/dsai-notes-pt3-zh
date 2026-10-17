# Comparing uninformed search strategies

Figure 3.21 compares search strategies in terms of the four evaluation criteria set forth in Section 3.3.2. This comparison is for tree-search versions. For graph searches, the main differences are that depth-first search is complete for finite state spaces and that the space and time complexities are bounded by the size of the state space.

| Criterion | Breadth-First | Uniform-Cost | Depth-First | Depth-Limited | Iterative Deepening | Bidirectional (if applicable) |
|---|---|---|---|---|---|---|
| Complete? | Yesᵃ | Yesᵃ,ᵇ | No | No | Yesᵃ | Yesᵃ,ᵈ |
| Time | O(bᵈ) | O(b^{1+⌊C*/ε⌋}) | O(bᵐ) | O(bˡ) | O(bᵈ) | O(b^{d/2}) |
| Space | O(bᵈ) | O(b^{1+⌊C*/ε⌋}) | O(bm) | O(bl) | O(bᵈ) | O(b^{d/2}) |
| Optimal? | Yesᶜ | Yes | No | No | Yesᶜ | Yesᶜ,ᵈ |

**Figure 3.21** Evaluation of tree-search strategies. *b* is the branching factor; *d* is the depth of the shallowest solution; *m* is the maximum depth of the search tree; *l* is the depth limit. Superscript caveats are as follows: ᵃ complete if *b* is finite; ᵇ complete if step costs ≥ ε for some positive ε; ᶜ optimal if step costs are all identical; ᵈ if both directions use breadth-first search.