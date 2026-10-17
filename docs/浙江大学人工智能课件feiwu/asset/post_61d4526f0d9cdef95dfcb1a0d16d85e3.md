
![](img/c69bfdf1f6addd09d49cae0440fcc5c7_939_0.png)
![](img/c69bfdf1f6addd09d49cae0440fcc5c7_939_1.png)
![](img/c69bfdf1f6addd09d49cae0440fcc5c7_939_2.png)
![](img/c69bfdf1f6addd09d49cae0440fcc5c7_940_0.png)
![](img/c69bfdf1f6addd09d49cae0440fcc5c7_940_1.png)
![](img/c69bfdf1f6addd09d49cae0440fcc5c7_940_2.png)

## Alpha-Beta Pruning: Move ordering

- **The effectiveness of alpha–beta pruning is highly dependent on the order in which the states are examined.**
  - For example, in Figure 5.5(e) and (f), we could not prune any successors of D at all because the worst successors (from the point of view of MIN) were generated first. If the third successor of D had been generated first, we would have been able to prune the other two.
    ![](img/c69bfdf1f6addd09d49cae0440fcc5c7_942_0.png)
- This suggests that it might be worthwhile to try to examine first the successors that are likely to be best.
- If this can be done, then it turns out that alpha–beta needs to examine only O(b<sup>m/2</sup>) nodes to pick the best move, instead of O(b<sup>m</sup>) for minimax.
- This means that the effective branching factor becomes \(\sqrt{b}\) instead of b—for chess, about 6 instead of 35. Put another way, alpha–beta can solve a tree roughly twice as deep as minimax in the same amount of time.
- If successors are examined in random order rather than best-first, the total number of nodes examined will be roughly O(b<sup>3m/4</sup>) for moderate b. For chess, a fairly simple ordering function (such as trying captures first, then threats, then forward moves, and then backward moves) gets you to within about a factor of 2 of the best-case O(b<sup>m/2</sup>) result.

m is the maximum depth of the tree and b are legal moves at each point.

## Properties of α-β

- Alpha–beta pruning is a search algorithm that **seeks to decrease the number of nodes** that are evaluated by the minimax algorithm in its search tree. It is an adversarial search algorithm used commonly for machine playing of two-player games (Tic-tac-toe, Chess, Go, etc.).
- The **benefit of alpha-beta pruning** lies in the fact that **branches of the search tree can be eliminated**. This way, the search time can be limited to the 'more promising' subtree, and a deeper search can be performed in the same time.
- The algorithm maintains two values, alpha and beta, which represent the maximum score that the maximizing player is assured of and the minimum score that the minimizing player is assured of respectively.
- Initially alpha is negative infinity and beta is positive infinity, i.e. both players start with their lowest possible score.
- It can happen that when choosing a certain branch of a certain node the minimum score that the minimizing player is assured of becomes less than the maximum score that the maximizing player is assured of (β ≤ α). If this is the case, the parent node should not choose this node, because it will make the score for the parent node worse. Therefore, the other branches of the node do not have to be explored.
- Pruning **does not** affect final result.
- Good move ordering improves effectiveness of pruning.
- With "perfect ordering," time complexity = O(b<sup>m/2</sup>).
  - → **doubles** depth of search

## Artificial Intelligence

## Statistical Learning and Modeling

PRML Chap.1

## Types of learning problems

- **Supervised learning problems**: applications in which the training data comprises examples of the input vectors along with their corresponding target vectors are known.
  - Classification and Regression
- **Unsupervised learning problems**: the training data consists of a set of input vectors **x** without any corresponding target values.
  - Density estimation
  - Clustering: k-means, mixture models, hierarchical clustering
  - Hidden Markov models
- **Reinforcement learning problem**: finding suitable actions to take in a given situation in order to maximize a reward. Here the learning algorithm is not given examples of optimal outputs, in contrast to supervised learning, but must instead discover them by a process of trial and error. A general feature of reinforcement learning is the trade-off between exploration and exploitation.
