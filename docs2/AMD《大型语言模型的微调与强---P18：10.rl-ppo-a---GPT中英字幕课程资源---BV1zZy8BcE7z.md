# AMD《大型语言模型的微调与强化学习：后训练入门｜Fine-tuning and Reinforcement Learning for LLMs》 - P18：10.rl-ppo-and-grpo-algorithms.zh_en - GPT中英字幕课程资源 - BV1zZy8BcE7z

![](img/e831b01dda084f2e994719b8ff9c05fc_0.png)

Two of the most popular RL training algorithms are PPO and GRPO。 Let's take a look at them。

 So here's where you're going to learn these new training objectives。

 So first revisiting the Rl training objective you just learned。

 you're trying to maximize sum of some probability term multiplied by some reward term So for better performance the probability term is a ratio between your model and reference Lm that generated the data or the rollouts and the reward term should be the advantage centered by a baseline and this leaves us with a question of how to compute the baseline be here to calculate the advantage there are a bunch of different ways and you'll see a couple of them in this video So the standard approach in PPO or proximal policy optimization which is used in RlHF is to train another model for the baseline and this model's only job is to predict the expected reward for each token and not just the full output sequence while the main LLm is generating so even halfway through generation and it's trained with regular supervised fine tuning using the actual rewards are。



![](img/e831b01dda084f2e994719b8ff9c05fc_2.png)

As the target labels Now this lets you compute advantages per token step。

 not just on the full response。 So tokens that contributed more or less to the final reward will get weighted differently。

 This is often implemented as the same Lm with a new head predicting the expected reward per token Now for per token of reward to be more accurate and smooth you'll want to use an advantage function estimator like Ge generalize advantage estimation GE uses the baseline model to backpro the final reward through earlier tokens。

 so earlier tokens get credit or blame for the final outcome so carries those prior rewards back with some discount factor。

 which is again another hyperparmeter and as a result Ge will smooth the rewards across tokens。

 the exact math is shown here but it's not important to know every single detail。

 It's just that this is actually what's used in practice for that estimation of advantage So this brings us to PPO proximal policy optimization and that's the first algorithm here and there's just one final。



![](img/e831b01dda084f2e994719b8ff9c05fc_4.png)

on the other ratio term sometimes that probability ratio can get really large too large and that can lead to huge unstable updates and PPO solves this by essentially clipping the ratio。

 So this math term is really just picking which one is smaller clipped or not clipped update and this prevents the weight updates from exceeding a certain threshold and large changes are therefore not allowed and this is the core idea of PPO actually takes small stable steps to prevent the model from breaking during training。

 All right and that was the full PPO training objective。

 So this is what PPO looks like in the whole R loop it's part of the training piece and just a look at it in a diagram you have your training objective great and you add clipping here。

 you train another LLM to estimate the baseline for your advantage you then update your main LLm using that PPO training objective to maximize reward and you loop All right the full PPO setup requires several different models the main LLM your training the frozen reference model and。



![](img/e831b01dda084f2e994719b8ff9c05fc_6.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_7.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_8.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_9.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_10.png)

Baseline estimation model that you're also training this is super computationally expensive and also complex to manage what's good is that this has led to newer algorithms that are more efficient and one of them is GRPO a group relative policy optimization and that's been introduced by deepse recently and GRPO's key innovation is that it gets rid of the separate baseline estimation model so the key innovation of GRPO over tpoO is stated here in the paper and it's a change to how the baseline is computed to get that advantage and that is the main thing but it is able to significantly reduce training resources right so exactly how does that happen remember the whole point of the baseline estimation model was to estimate the baseline reward so that the outputs are clustered around zero and credit for the reward is distributed across the tokens more fairly and only tokens that did better or worse than expected get strong learning signals this definitely reduces that variance and distributes credit across the sequence more effectively GRPO asks instead of training。



![](img/e831b01dda084f2e994719b8ff9c05fc_12.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_13.png)

Whole separate model to predict the average or expected reward。

 Why not just generate a group of several outputs for a single input and calculate the actual average reward of that group That is the key idea of grRPO It's really simple and it's a direct way to estimate the baseline on the fly and specifically GRPO computes the baseline by literally drawing many different outputs and that's part of a group for every single input and then subtracting out the average reward and dividing by the standard deviation and this obvious a need for that extra model。

 but it does require more sampling and so that's GO's advantage calculation Now to go into it encode a little bit you can specify a certain number of outputs you want to sample and what temperature to use to get those variations and temperature just helps you sample different outputs per input So pulling back to the Rl training objective GRPO's objective will be very similar to BpoO but the baseline is no longer that prediction from another model instead the baseline is just the average of the raw rewards for。

outputputs of a single input， basically that group and encode this is what the baseline equation looks like just normalizing the rewards over different sequences pretty simple so note that the advantage estimation is now at the sequence level and no longer at the token level like in PPO so just go through a concrete example。

 maybe you sample four outputs from a single input and then you have different graders like formatting or unit test to give an aggregate reward for every single output like this。



![](img/e831b01dda084f2e994719b8ff9c05fc_15.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_16.png)

Then the baseline is the average of these scores so you can then calculate the advantage for each response by subtracting that baseline。

 note that in the raw rewards， it's all positive right but then now the advantage you're actually getting that distribution and they're centered around zero and then responses A and B will have that positive advantage So Rl update will increase their probability and C and D will have negative advantage so their probability will be decreased All right so here's GRPO it keeps the clipping and PPO and just changes the advantage calculation Now going through it a bit here So your grRPO objective here is to weight the probability of next token by advantage with clipping similar to PPO but instead your advantage calculation is going to be different。

 so you want to normalize rewards in a group of outputs then you update your Lm using this objective to maximize the reward just like in PPO and you in your code。

 this is what it'll look like So for a particular input you generate a group of outputs so just multiple outputs for a unique input then you compute the rewards for that group。



![](img/e831b01dda084f2e994719b8ff9c05fc_18.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_19.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_20.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_21.png)

And then you get the average reward to then calculate the advantage pretty simple and then you pass this compute reward function as the reward function pass your GRPO arguments in and your data sets in and then your model in and then you can train So GRPO essentially gets rid of this model out of these four different models which is great because you're also usually training this one in PPO and that takes up a lot of space not to mention it can be some unstable as well All right so here's the full comparison of PPO in GRPO there's still quite a few similarities overall but the key differences are one you see the baseline estimation model it's gone and then you can see the advantage calculation being very different one using the baseline estimate or the expected reward per token and the other using that group computation。

 Okay so this has been pretty thrilling to learn here's a bit of the history of the methods you've learned So from RLHF with PPO ahead of chat QT's launch to R AIF where AI is giving feedback instead of humans to abide by that constitution。



![](img/e831b01dda084f2e994719b8ff9c05fc_23.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_24.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_25.png)

To GRPO and using GRPO with verifiers and reward models to effectively reason So here's looking at the whole view again。

 where you put in PPO or GRPO， it's really here where you're defining your RL training objective so going through that loop。

 your training objective can be either PPO or GRPO and you update your LM again by maximizing the reward in you loop。



![](img/e831b01dda084f2e994719b8ff9c05fc_27.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_28.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_29.png)

![](img/e831b01dda084f2e994719b8ff9c05fc_30.png)

Congratulations on getting to the end of module2 oof。

 that was tough with all of that math but I hope you got some intuition on fine tuning and reinforcement learning Next up。

 take a look at how evaluation your test sets， your Eval sets will actually help guide that training process as a North Star。

