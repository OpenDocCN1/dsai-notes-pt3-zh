# 阿尔伯塔大学【中英⚡强化学习｜Reinforcement Learning Specialization】 p44 P44 02_使用蒙特卡洛方法进行广义策略迭代 -BV1CdGrzuEJU_p44-

Now that we can estimate action values using Monte Carlo。

 the next step is to build a generalized policy iteration algorithm。

Let's see how we can do that today。By the end of this video。

 you will understand how to use Monte Carlo methods to implement a GI algorithm。

GPI includes a policy evaluation and a policy improvement step。

GPI algorithms produce sequences of policies that are at least as good as the policies before them。

For the policy improvement step， we can make the policy greedy with respect to the agent's current action value estimates。

For the policy evaluation step， we will use a Monte Carlo method to estimate the action values。

Remember that in the GI framework， the value estimates need only improve a little。

 not all the way to the correct action values。All that is required for convergence is that the estimates continue to improve。

MoonD Carlo control methods combined policy improvement and policy evaluation on an episode by episode basis。

Now let's put these two together in one algorithm。

![](img/c79e97fb443f1c49ab0d8d256d3328a0_1.png)

Let's start with our Monte Carlo method for learning A values。

You use exploring starts so that each episode begins with a randomly selected state and action。

Then the agent generates an episode by following his policy。

 keeping track of the state's actions and rewards along the way。Once the episode is complete。

 it computes each return starting from the end of the episode。

Then it adds their return to the appropriate list。The lists of returns are then averaged to update the action value estimates for each state action pair。

This completes the policy evaluation step。After policy evaluation。

 it's time to do policy improvement。 We simply update the policy to take the greedy action with respect to our updated action values。

We do this in every state observed during the episode。

Isn't this so much easier than the way we did this step in dynamic programming？And that's it。

This is the generalized policy iteration algorithm， Mon Carlo with exploring starts。



![](img/c79e97fb443f1c49ab0d8d256d3328a0_3.png)

![](img/c79e97fb443f1c49ab0d8d256d3328a0_4.png)

In this video， we described how to use Monte Carlo methods within the GPI framework。

And discuss an example GPI algorithm called Monte Carlo with exploring starts。

