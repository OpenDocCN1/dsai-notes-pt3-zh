

## Learning heuristics from experience

Inductive learning methods work best when supplied with features of a state that are relevant to predicting the state’s value, rather than with just the raw state description. For example, the feature “number of misplaced tiles” might be helpful in predicting the actual distance of a state from the goal. Let’s call this feature _x_<sub>1</sub>(_n_). We could take 100 random generated 8-puzzle configurations and gather statistics on their actual solution costs. We might find that when _x_<sub>1</sub>(_n_) is 5, the average solution cost is around 14, and so on. Given these data, the value of _x_<sub>1</sub> can be used to predict _h_(_n_). Of course, we can use several features. A second feature _x_<sub>2</sub>(_n_) might be “number of pairs of adjacent tiles that are not adjacent in the goal state.” How should _x_<sub>1</sub>(_n_) and _x_<sub>2</sub>(_n_) be combined to predict _h_(_n_)? A common approach is to use a linear combination:

\(h(n)=c_1x_1(n)+c_2x_2(n).\)

The constants _c_<sub>1</sub> and _c_<sub>2</sub> are adjusted to give the best fit to the actual data on solution costs. One expects both _c_<sub>1</sub> and _c_<sub>2</sub> to be positive because misplaced tiles and incorrect adjacent pairs make the problem harder to solve. Notice that this heuristic does satisfy the condition that _h_(_n_)=0 for goal states, but it is not necessarily admissible or consistent.

## Summary

We have introduced methods that an agent can use to select actions in environments that are deterministic, observable, static, and completely known. In such cases, the agent can construct sequences of actions that achieve its goals; this process is called **search**

- Before an agent can start searching for solutions, a **goal** must be identified and a well defined **problem** must be formulated.
- A problem consists of five parts: the **initial state**, a set of **actions**, a **transition model** describing the results of those actions, a **goal test** function, and a **path cost** function.
- The environment of the problem is represented by a **state space**. A path through the state space from the initial state to a goal state is a **solution**.
- Search algorithms treat states and actions as **atomic**: they do not consider any internal structure they might possess.

## Summary

We have introduced methods that an agent can use to select actions in environments that are **deterministic**, **observable**, **static**, and **completely known**. In such cases, the agent can construct sequences of actions that achieve its goals; this process is called **search**

- A general TREE-SEARCH algorithm considers all possible paths to find a solution, whereas a GRAPH-SEARCH algorithm avoids consideration of redundant paths.
- Search algorithms are judged on the basis of **completeness**, **optimality**, **time complexity**, and **space complexity**. Complexity depends on b, the branching factor in the state space, and d, the depth of the shallowest solution.

## Summary

**Uninformed search** methods have access only to the problem definition. The basic algorithms are as follows:

- **Breadth-first search** expands the shallowest nodes first; it is complete, optimal for unit step costs, but has exponential space complexity.
- **Uniform-cost search** expands the node with lowest path cost, g(n), and is optimal for general step costs.
- **Depth-first search** expands the deepest unexpanded node first. It is neither complete nor optimal, but has linear space complexity. **Depth-limited search** adds a depth bound.
- **Iterative deepening search** calls depth-first search with increasing depth limits until a goal is found. It is complete, optimal for unit step costs, has time complexity comparable to breadth-first search, and has linear space complexity.
- **Bidirectional search** can enormously reduce time complexity, but it is not always applicable and may require too much space.

