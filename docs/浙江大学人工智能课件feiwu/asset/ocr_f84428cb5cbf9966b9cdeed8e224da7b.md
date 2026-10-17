# Upper Confidence Bounds on Trees (UCT)

+   - Each game ends after the very first action, with the player receiving a stochastic reward that depends only on the selected action. The challenge is to maximize the player's total expected reward, i.e., quickly find the action with the highest expected reward, without losing too much reward along the way.

+   - One simple, yet effective, strategy is to always select the action whose value estimate is the largest, with an optimistic adjustment that takes account of the uncertainty of the value estimate. This way, each action either results in an optimal action or in a reduction of the uncertainty associated with the value estimate of the chosen action. Thus, suboptimal actions cannot be chosen indefinitely.