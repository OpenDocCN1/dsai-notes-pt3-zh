# 【阿尔伯塔大学】完整的强化学习系统 ｜ Complete Reinforcement Learning System p14 P14_代理架构-与玛莎的会议-设计选择概述 _04_01_01 -BV1VHYJz1Ee8_p14-

You are now in the third week of the capstone project。

 which means we are halfway through building a complete RL system。

So far we have formalized the Lunar Lander problem using the language of MDPs last week we discussed which algorithm to use to solve that MDP。

Now let's discuss the metaparameter choices that you will have to make to fully implement the agent。

This means we need to decide on the function appximator。

 choices in the optimizer for updating the action values， and how to do expiration。

So which function appromator will you use My general advice is to always start simple for function approximation。

 that would mean using a fixed basis like tile coding。Unfortunately。

 that might not be the best choice for this problem without carefully designing the tilecoder。

If you tile all the inputs together， the number of features grows exponentially with the input dimension for example。

 if you want to use 10 tiles per dimension for this eight dimensional problem。

 you could easily end up with 100 million features。

So maybe we should consider using a neural network instead。

One hidden layer should be sufficiently powerful to represent the value function for lunar lander。

 and it will be a bit easier for you to implement。We need to decide the number of hidden units in that layer。

 remember that you get to choose the size of the hidden layer of a neural network as you add more nodes to a layer。

 you add more representational power。 however， the more nodes you add。

 the more parameters there are to learn。We also need to pick the activation functions。

We could use a sigmoidal function like tan0 H， but these have some issues with saturation。

Think about when the inputs to the activation function are high magnitude。

 either positive or negative， the gradient is computed in these flat regions of the activation。

Such a gradient near zero does not provide much signal to change our weights and can slow learning。

We can also use a linear threshold unit or LTU， but again。

 these flat regions make it hard to train the neural network。

A pretty effective and common choice is to use rectified linear units or rail use。

 so let's go ahead with those。We also need to discuss how we are going to train the neural network。

 using vanillato castastic gradient descent will likely be too slow for this project。

 so what are our other options？We could try this algorithm called8degrad The downside to this is that8eggrad decays the step sizes towards zero。

 which can be problematic for nons stationationary learning。We could try RMS Pro。

 which uses information about the curvature of the loss to improve the descent step。However。

 we'd like to also incorporate momentum to speed up learning。

A good choice could be the atom optimizer， this combines the curvature information from RMS Pro and momentum。

We finally need to discuss which exploration method we will use What about optimistic initial values？

This would be a reasonable choice if we were using a linear function appximator with non negative features。

But since we are using a neural network， it is difficult to maintain optimistic values and so is unlikely to be effective。

We could also consider epsilon greedy， this is very straightforward to implement。

The downside though is that its exploration completely ignores whatever information the action values might have。

 it is equally likely to explore an action with really negative value as an action with moderate value。

I know how about we use a softftmax policy？This choice could be better because the probability of selecting an action is proportional to the value of that action。

This way， we are less likely to explore actions that we think are really bad。By the way， in course3。

 we only talked about softftmax policies on action preferences。

 we use policy gradient methods to adjust the action preferences。

 but it is not a big leap to consider using an action value method like expected SArsRSA and use a softmax directly on the learned action values。

There are a few things to consider when using a softmax on the action values First。

 let's think about how it affects the expected SARSSA update remember that we need to compute the expectation over action values for the next state。

This means we'll need to compute the probabilities for all the actions first under the Softmax function。

Next， we also need to consider how much the agent focuses on the highest value actions。

We can show this with a temperature parameter called tau。If Tu is large。

 then the agent is more stochastic and selects more of the actions for very large Tau。

 the agent behaves nearly like a uniform random policy。For a very small tau。

 the agent mostly selects the greedy action。Finally。

 we need to consider an additional trick to avoid overflow issues when computing the softftmax。

Imagine that the action values are large。Exponentiating those values can get very large Instead。

 we can use the fact that subtracting a constant from the action values when computing the probabilities has no effect for example。

 we can subtract the maximum action value divided by the temperature then all the exponents are negative and we avoid taking the exponent of large positive numbers。

Altogether， we now have a reasonable strategy to learn an optimal soft policy that also explores a bit more intelligently than epsilon greedy。

The agent takes actions according to its current softftmax policy and uses expected SArsRSA updates。



![](img/a94bfb91e541697612c309f5a5a23d6a_1.png)

And that's it for this video today we brainstorm some of the key choices in your agent Overall there are a lot of choices to make most of these choices we set by reasoning through what might be the most appropriate like we did for the choices in the function appximator。

Other choices like specific step sizes in the optimizer or exploration parameters like the temperature can be less obvious to simply select we will discuss more ways to determine these parameters in module 5 See you then。



![](img/a94bfb91e541697612c309f5a5a23d6a_3.png)