# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p22 P22 动态感知的无监督技能发现（论文解析） [BV1o3xLznExj_p22]

Hi there， take a look at this humanoid right here。It walks from one checkpoint to another checkpoint and then to the next checkpoint and so on。

 and that is its task， it gets reward from walking from checkpoint to checkpoint。



![](img/bbe75fccced54f07faf698943b720504_1.png)

![](img/bbe75fccced54f07faf698943b720504_2.png)

![](img/bbe75fccced54f07faf698943b720504_3.png)

Take a look at this and。 is called the end。 It also walks from checkpoint to checkpoint。 Now。

 we've seen a lot of reinforcement learning algorithms in this environment。

 It's called Mukojo where you basically teach these little things to walk around。

 So what's the impressive part here， the impressive part is that at training time， this an has never。

 ever seen what a checkpoint is， and has never gotten any reward from walking from checkpoint to another checkpoint。

 Actually， it has never gotten any reward for anything that that is given from the environment。

 It has discovered the skill of walking by itself。 And then at test time。



![](img/bbe75fccced54f07faf698943b720504_5.png)

![](img/bbe75fccced54f07faf698943b720504_6.png)

![](img/bbe75fccced54f07faf698943b720504_7.png)

![](img/bbe75fccced54f07faf698943b720504_8.png)

![](img/bbe75fccced54f07faf698943b720504_9.png)

![](img/bbe75fccced54f07faf698943b720504_10.png)

![](img/bbe75fccced54f07faf698943b720504_11.png)

![](img/bbe75fccced54f07faf698943b720504_12.png)

![](img/bbe75fccced54f07faf698943b720504_13.png)

There is no additional learning when it goes from checkpoint to checkpoint。

 It simply composes the skills that it knows from its unsupervised discovery phase in order to to go from checkpoint to checkpoint。



![](img/bbe75fccced54f07faf698943b720504_15.png)

![](img/bbe75fccced54f07faf698943b720504_16.png)

![](img/bbe75fccced54f07faf698943b720504_17.png)

So here you can see this paper basically proposes to learn these skills in an completely unsupervised way at the beginning sort of in the training phase。

 it learns these skills。 you can see these skills that the humanoid has learned。

 and then all you have to do at test time is to compose these skills to reach a given goal and these are the things that the ant has learned watch out。

 this is trippy。 you can see it has learned various walks， various ways of walking here。

 And if you know anything about this environment。 It's actually not that easy to make the ant walk by itself。

 So the the discovery here that these skills that are discovered or various ways of walking is actually already pretty impressive。



![](img/bbe75fccced54f07faf698943b720504_19.png)

![](img/bbe75fccced54f07faf698943b720504_20.png)

![](img/bbe75fccced54f07faf698943b720504_21.png)

![](img/bbe75fccced54f07faf698943b720504_22.png)

![](img/bbe75fccced54f07faf698943b720504_23.png)

And the last thing here， this cheetah， of course， also has to， has learned to walk back forward。

 kind of jump around and so on。 So we're going to dive into this paper。 It's called Dynamics Aware。

 unsupervised discovery of skills by Archie Charrma and other people of Google Brain。



![](img/bbe75fccced54f07faf698943b720504_25.png)

![](img/bbe75fccced54f07faf698943b720504_26.png)

So this was published at ICClLear 2020 and on a high level。

 I already said it's basically proposing to learn unsupervised skills and then to compose these skills in a model based planning method at test time to reach a given goal without additional training。

 without additional training on the reward that you give at test time。As always。

 if you like videos like this， you're very welcome to subscribe and share it to everyone you know。

Yeah， okay， that's dive in。So， they say。Conventionally。

 model based reinforcement learning aims to learn a global model for the dynamics of the environment which。

Is not exactly true right So we dive into model based and model3 reinforcement learning Model based reinforcement learning basically means that you have a model of the environment。

 A example for this is let's say a tick ta toe。So in ti ta toe。

 I know I I I have 9 actions at my disposal。 And if I take action， let's say I take action 0。

 which is to make a。Let's say I'm the X player。 So I take action 0。 and if I， you know。

 number my things correctly， then that will result in this state of the world。 Okay。

 so I know exactly how the world will look when I take a given action。

 And what that allows me to do is that allows me to actually plan。 So I cannot plan ahead。

 I can say what would happen if I took action 0。 So I can do this in my mind。

 and then what would happen if I took action 1， I can be like。Okay， that's going to happen。

 and I can do this with many things， and I can in my mind。

 continue this and basically roll out to the entire games。Or， and then。

Only do the given action that has LED to the best result at the end right So this is model model based reinforcement learning means you have a model of the environment。

 You know what's going to happen when you perform given actions。

 and you can also combine this with machine learning like you know， Al Al go。

 Al 0 or so they have models of the games they're playing， they know what's going to happen。

 but it's very interactable to basically go down this entire tree and plan out everything。

 So they combine it with machine learning。It doesn't change that it's model based。

Now in opposition to that in Model3 in reinforcement learning， what you do you are this agent。

 the heres the environment and you simply have to do an action。

 I do action  zero and the environment just gives you back a reward and the next observation and you have basically no clue how the environment will change if you do something all all these agents do or the classic model3 agents do is basically they're trying to have a neural network。

Somewhere in them and you put the observation in here and outcomes in action and you can do this in various ways you do Q learning or policy gradient or actor critic and so on but ultimately it's simply mapping the opt the current observation and maybe the last view to the best action to take without explicitly modeling what happens in the environment Now when they say modelbased reinforcement learning what they mean is technically what you can do ifre if you are in the model free if you' are in this situation what you could do is you could say。

 well， since these modelbased Rl techniques tend to work better， I could here inside the agent。

 I could try to learn a model of the environment E prime and I could try to basically learn what happens in my environment when I do a certain action and then I could use that model right here。

In order to do this planning that I know from up here。In， in this case。They go for exactly this。

 They go for， let's learn a model of the environment。 This is not an exact model。

 It's a learned model。 And then let's use that to plan。 Now， this usually has a bunch of， you know。

 very。A bunch of things that go against it。 namely， if this model right here is bad。

 then the planning in the model will ex often accumulate and even exaggerate the errors that are in this model。

 So it's sometimes very hard to learn a model of the world and then use that for planning。

 And I've recently done a paper where， where curious AI takes。

The noising auto encoders to regularize exactly such a planning procedure to counter this。

This paper right here is a different approach of combining this learned model。This learned model。So。

 okay。That was about the first sentence。They say it aims to learn a global model for the dynamics of the environment。

 A good model can potentially enable planning algorithms to generate a large variety of behaviors and solve diverse task。

 which is true， right， if I have a model of the environment， then I could just use it to plan。

 I wouldn't even have to do anything fancy anymore， if I have a model of how my Titto works。

 I can just plan plan my way to success。 And I can do this alpha zero style or if if this state tree is small enough。

 I can actually just use a planner。 And I don't even have to， I don't have to do anything anymore。

 if I have a good model。😊，They say however learning and accurate model for complex dynamical systems is difficult。

 and even then the model might not generalize well outside the distribution of states on which it was trained。

 So this is another problem。 If you learn a model， it's only going to be valid in a certain range okay。

And say in this work， we combine。Model based learning。With model free learning。

And the model free learning is of primitives that make model based planning easy。

So what they attempt to do is they attempt in an unsupervised fashion to learn so called set of skills。

 and the set of skills could be something like walk forward。Walk backward。Stay put。jump。

So they attempt to learn things like this in a model free way so that the model is simply asked to come up with these things or the agent is simply asked task to come up with these things and then in stage two。

 a planner can use these skills and decompose a plan now this plan here。

The special thing about this plan， this planner， it doesn't operate in the space of actions of。



![](img/bbe75fccced54f07faf698943b720504_28.png)