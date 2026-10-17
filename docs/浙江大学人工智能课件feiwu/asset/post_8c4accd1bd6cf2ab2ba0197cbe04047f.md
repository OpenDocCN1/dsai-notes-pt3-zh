
## Monte-Carlo Tree Search

### Backpropagation

- Moves backward through saved path; value of node is representative of benefit of going down that path from parent.
- Values are updated dependent on board outcome.
- Based on how the simulated game ends, values are updated.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_88_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_89_0.png)

Fig. 2. One iteration of the general MCTS approach

Figure 2 shows one iteration of the basic MCTS algorithm. Starting at the root node t₀, child nodes are recursively selected according to some utility function until a node tₙ is reached that either describes a terminal state or is not fully expanded (note that this is not necessarily a leaf node of the tree). An unvisited action a from this state s is selected and a new leaf node tₗ is added to the tree, which describes the state s′ reached from applying action a to state s. This completes the tree policy component for this iteration.

A simulation is then run from the newly expanded leaf node tₗ to produce a reward value Δ, which is then backpropagated up the sequence of nodes selected for this iteration to update the node statistics; each node’s visit count is incremented and its average reward or Q value updated according to Δ. The reward value Δ may be a discrete (win/draw/loss) result or continuous reward value for simpler domains, or a vector of reward values relative to each agent p for more complex multi-agent domains.

As soon as the search is interrupted or the computation budget is reached, the search terminates and an action a of the root node t₀ is selected by some mechanism.

### Upper Confidence Bounds on Trees (UCT)

- An extremely desirable property of any game-tree search algorithm is **consistency**, i.e., given enough time, the search algorithm will find the optimal values for all nodes of the tree, and can therefore select the optimal action at the root state. The UCT algorithm is a consistent version of Monte-Carlo tree search.
- If all leaf value estimates were truly the optimal values, one could achieve consistency at the parent nodes by applying greedy action selection, which simply chooses the action with the highest value in each node. If all descendants of a given node have optimal value estimates, then greedy action selection produces optimal play from that node onwards, and therefore simulation will produce an optimal value estimate for that node. By induction, the value estimate for all nodes will eventually become optimal, and ultimately this procedure will select an optimal action at the root.
- However, the value estimates are not usually optimal for two reasons:
  1. the policy is stochastic, so there is some inherent randomness in the values.
  2. the policy is imperfect. Thus, going with the action that has the highest value estimate can lead to suboptimal play, e.g., if the value of the optimal action was initially underestimated. Therefore, occasionally at least, one must choose actions that look suboptimal according to the current value estimates.
- The problem of when and how to select optimal or suboptimal actions has been extensively studied in the simplest of all stochastic action selection problems. These problems are known as **multi-armed bandit problems**.
- Each game ends after the very first action, with the player receiving a stochastic reward that depends only on the selected action. The challenge is to maximize the player's total expected reward, i.e., quickly find the action with the highest expected reward, without losing too much reward along the way.
- One simple, yet effective, strategy is to always select the action whose value estimate is the largest, with an optimistic adjustment that takes account of the uncertainty of the value estimate. This way, each action either results in an optimal action or in a reduction of the uncertainty associated with the value estimate of the chosen action. Thus, suboptimal actions cannot be chosen indefinitely.
