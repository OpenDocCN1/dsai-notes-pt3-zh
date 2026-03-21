# 阿尔伯塔大学【中英⚡强化学习｜Reinforcement Learning Specialization】 p106 P106 05_基于函数逼近的期望Sarsa算法 -BV1CdGrzuEJU_p106-

![](img/df6e97b620f973938f0dc76c9ee3b8dc_0.png)

So far we've talked about using SArsRSA with function approximation。

 let's continue our journey through approximate control methods and look at expected SArsSA。

By the end of this video， you'll be able to explain the update for expected SARSSA with function approximation and explain the update for Q learning with function approximation。

Let's see how we can turn SARSA into expected SARSSA when using function approximation。

Recall the update equation for SARSSA。SARSA's update target includes the action value for the next state and action。

Now recall that expected SARSSA instead uses the expectation over its target policy to compute the expectation we simply sum over the action values weighted by their probability under the target policy。



![](img/df6e97b620f973938f0dc76c9ee3b8dc_2.png)

The same expectation can be computed even when we use function approximation。

Let's see how to do this。First， recall the update for SArsRSA with function approximation。

It looks similar to the tabular setting， except the action value estimates are parameterd by the weight vector W。

We also have a gradient term to distribute the error to the weights appropriately。

Expected SArsa with function approximation follows a similar structure。

 we compute the action values from a weight vector for every action in the next state。

Then we compute his expectation under the target policy。

And that's all we have to do to change SARSA into expected SARSA。



![](img/df6e97b620f973938f0dc76c9ee3b8dc_4.png)

Now how do we do this for Q learning with function approximation？Fortunately。

 Q learning is a special case of expected SARSA in Q learning。

 the target policy is greedy with respect to the approximate action values。

Computing the expectation under greedy policy is the same as computing the maximum action value。

So the Q learning update with function approximation is actually quite straightforward。

We just use the max in place of the expectation。

![](img/df6e97b620f973938f0dc76c9ee3b8dc_6.png)

And that's it for this short video today we introduced expected SARSSA with function approximation and we also showed how to extend it to Q learning with function approximation。

Next time we'll think about how to do exploration with function approximation until then。

 don't get lost。