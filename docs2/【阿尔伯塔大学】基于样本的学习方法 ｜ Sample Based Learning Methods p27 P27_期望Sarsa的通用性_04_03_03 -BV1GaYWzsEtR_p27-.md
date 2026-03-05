# 【阿尔伯塔大学】基于样本的学习方法 ｜ Sample Based Learning Methods p27 P27_期望Sarsa的通用性_04_03_03 -BV1GaYWzsEtR_p27-

![](img/e5005edfdcf2cee6355335e46dd75cc8_0.png)

Up until now， we've seen three TD algorithms for control， SArsSA， Q learning， and expected SASA。

Two of those algorithms， SARSSA and expected SARSSA， both approximate the same beman equation。Today。

 let's look at how expected SARSSA is related to Q learning。



![](img/e5005edfdcf2cee6355335e46dd75cc8_2.png)

By the end of this video， you will understand how expected SArsRSSA can do off policy learning without using important sampling。

And explain how expected SARSA generalizes Q learning。Let's start with the on policy case。

 where the behavior policy and the target policy are equal。Consider the expected SArsSA update。

The next action is sampled from piI in this case。However。

 notice that the expectation over actions is computed independently of the action actually selected in the next state。

😊，In fact， P need not be equal to the behavior policy。This means that expected SArsSA。

 like Q learning， can be used to learn off policy without important sampling。

Now what happens if the target policy is greedy with respect to its action value estimates。

 we can see that only the highest value action is considered in the expectation。

This is equivalent to computing the maximum over actions in the next state， just like in Q learning。

In other words， Q learning is a special case of expected SArsSA。



![](img/e5005edfdcf2cee6355335e46dd75cc8_4.png)

In this video， we showed that expected SARSSA and Q learning both use the expectation over their target policies in their update targets。

This allows them to learn off policy without important sampling。

Expected SArsRSA with a target policy that's greedy with respect to its action values is exactly Q learning。

