# # Iterative deepening depth-first search

# ## Iterative deepening search (IDS)

```
```
function ITERATIVE-DEEPENING-SEARCH(problem) returns a solution, or failure
  for depth = 0 to ∞ do
    result ← DEPTH-LIMITED-SEARCH(problem, depth)
    if result ≠ cutoff then return result
```
```

**Figure 3.18** The iterative deepening search algorithm, which repeatedly applies depth-limited search with increasing limits. It terminates when a solution is found or if the depth-limited search returns failure, meaning that no solution exists.

+   - the total number of nodes generated in the worst case is:
+     
+     N(IDS) = (d)b + (d − 1)b² + ⋯ + (1)bᵈ

+   - E.g. b=10, d=5
+     - N(IDS) = 50 + 400 + 3,000 + 20,000 + 100,000 = 123,450
+     - N(BFS) = 10 + 100 + 1,000 + 10,000 + 100,000 = 111,110