As the problem progresses, we can assume restrictions about the range of possible solutions based on **Min** nodes (which may place an upper bound) and **Max** nodes (which may place a lower bound). As we move through the search tree, these bounds typically get closer and closer together:

![](bbox=[0.16, 0.301, 0.725, 0.428])

This convergence is not a problem as long as there is some overlap in the ranges of alpha and beta. At some point in evaluating a node, we may find that it has moved one of the bounds such that there is no longer any overlap between the ranges of alpha and beta. At this point, we know that this node could never result in a solution path that we will consider, so we may stop processing this node. In other words, we stop generating its children and move back to its parent node. For the value of this node, we should pass to the parent the value we changed which exceeded the other bound.

![](bbox=[0.182, 0.82, 0.703, 0.928])