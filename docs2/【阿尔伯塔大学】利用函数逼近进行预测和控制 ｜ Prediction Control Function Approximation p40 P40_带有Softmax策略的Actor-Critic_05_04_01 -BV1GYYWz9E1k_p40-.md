# 【阿尔伯塔大学】利用函数逼近进行预测和控制 ｜ Prediction Control Function Approximation p40 P40_带有Softmax策略的Actor-Critic_05_04_01 -BV1GYYWz9E1k_p40-

![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_0.png)

Acctor critic elegantly mixes direct policy optimization， value functions。

 and temporal difference learning。The aritic method we discussed previously was quite general。

 we didn't specify the function approximation， nor the policy parameterization。

Today we discuss one specific implementation， actor critic with linear function approximation and a soft max policy parameterization。

By the end of this video， you'll be able to derive the a critictic update for a Softmax policy with linear action preferences and implement this algorithm。

Previously we introduced the Actctor critictic algorithm， that algorithm combines policy evaluation。

 which is the critic and the policy gradient rule to update the policy， which is the actor。

The critic uses semi gradient TD。The actor uses the TDR from the critic to update the policy parameters。



![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_2.png)

All of this is a little bit high level and abstract， let's consider a specific implementation。

Let's build an algorithm for a finite set of actions and continuous states。

A common choice of policy parameterization for finite actions is the softmax policy we discussed before。

We can use function approximation to represent the preferences。

The parameters of this function are the policy parameters denoted by theta。

 so our policy grading learning rule will update theta。

 We use a softm policy that expentiates the preferences and divides by the sum。

This guarantees the resulting action probabilities are positive and sum to one。

Notice the policy is written as a function of the current state。

 this is like having a different softmax distribution for each state。

Watch the agent move through the state space。

![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_4.png)

The state dependent action preferences give rise to potentially different distributions for each state。



![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_6.png)

To select an action， we follow a simple procedure in the current state we query the softm for each action。



![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_8.png)

This generates a vector of probabilities， one entry for each action。Given this vector。

 we pick an action proportionally to these probabilities。



![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_10.png)

Now let's discuss how our parameterization choices impact the value function， the action preferences。

 and our update equations。Let's use the same features for our value estimates and the policy。

Remember， the critic updates an estimate of the state value function。

So the critic only requires a feature vector characterizing the current state。

The actor's action preferences depend on the state and action。

So our action preference function requires a state action feature vector。

We have encountered this issue before。We use the same strategies before， stacked state features。

 that is we use a copy of the state feature vector for each action。

The size of the policy parameter vector theta is larger than the weights W used by the critic。

 since there are three actions， this is three times larger。



![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_12.png)

Now let's look at the update equations for the actor and the critic with our linear Softmax parameterization。

The first one is easy。The gradient of the linear value function is just the feature vector。

So the critic's weight update is just alpha times the TDR times the feature vector。

Same old semi gradient TD， the actor's update to the preferences requires a bit more thought。Luckily。

 the gradient is not so bad， we will leave out the derivation and just give you the final result。

 You can verify it if you like。The gradient has two parts。

 the first is the state action features for the selected action。

The second part is the state action features multiplied by the policy summed over all actions。



![](img/c48c1e06f88fa11ee9ace1ffb955ebb2_14.png)

That's it for this video Today we discussed a specific implementation of actor critictic。

Now you know everything you need to know to implement this algorithm on your own。

Next time we'll try this algorithm mode and see how it works。 I can't wait。

