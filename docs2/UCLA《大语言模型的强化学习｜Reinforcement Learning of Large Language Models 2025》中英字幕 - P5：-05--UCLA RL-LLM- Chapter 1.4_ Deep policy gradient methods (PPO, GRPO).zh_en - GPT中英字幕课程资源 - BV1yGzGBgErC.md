# UCLA《大语言模型的强化学习｜Reinforcement Learning of Large Language Models 2025》中英字幕 - P5：-05--UCLA RL-LLM- Chapter 1.4_ Deep policy gradient methods (PPO, GRPO).zh_en - GPT中英字幕课程资源 - BV1yGzGBgErC

![](img/294d57c980c5d60a2c8cbbc42365d5aa_0.png)

So the A 3 C method or the A2 C method is， it's nice in many ways， but it has one drawback。

 And the drawback is that it has poor sample efficiency。

 So what is sample efficiency in machine learning， sample efficiency efficiency refers to the methods。

 a methods ability to learn with fewer data points。 In comparison。

 humans have very good sample efficiency， we can learn with just a handful of experiences。

 While in general， machine learning models require a lot of data to be able to learn a certain concept。

 But even among machine learning methods， some are more sample efficient。

 Some are less sample efficient。😊，For reinforcement learning in simulateimd environments。

 such as when learning to play the Atari 2600 video games。

 sample efficiency is actually not a concern at all。

 and only the compute efficiency matters in an environment such as Atari 2600 where we have a full emulator samples are free。

 the only thing that costs is compute time。But in many Ral setups， however。

 samples here I mean by what I mean by samples are full trajectories of episodes or sample state and action pairs。

 these are obtained by interacting with the environment， and this can be expensive。And in such cases。

 we prefer methods with good sample efficiency。 So， for example。

 let's say we are trying to train a physical robot to do something in the real world。 Well。

 in order to obtain samples in this RL environment， you need to have a physical robot。

 The physical robot will need to take certain actions within the real world which might have certain costs。

 It will cost fuel。 It might break things So that's a cost and also physical robot can at most operate 24 hours a day and the operation and each robot will be expensive。

 So theres there's a cost to this。 as another example。

 when you have a large language model writing a completion and having a human provide feedback as to whether the completion was good。

 Well the human reading an LLM completion and providing a feedback Well， that's a very costly thing。

 you need to pay these human hourly wages to provide such feedback。

 and you would want the learning algorithm to be sample efficient with respect to these costs。😊。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_2.png)

Hum feedback。So how can we learn more from an episode tau。 Well。

 the algorithm A to C uses an episode to perform T SGD updates。 Now。

 can we learn more from a given episode tau， can we be a little bit more sample efficient。 Well。

 the issue with a to C is that for each time step， there is at most one stochastic gradient that's obtained。

 And then that transition is basically forgotten。 But maybe there is more than one gradient step worth of information that can be extracted from a particular transition and A to C uses an episode tau to perform T SGD updates And since each episode has T time steps that's one SGD update per time step。

😊，Okay， so to extract more information from an episode。

 one approach is to use what's called a surrogate objective。

 Let theta and theta not be a policy parameters。 And let's consider the objective function evaluated at theta versus theta 0。

 So here we have J theta minus J theta n。 Let's go through some calculation calculations。

 So J theta not is by definition the value function with respect to the policy pi theta not。

 So this is the parameterized policy pi with the parameter value theta not。

 we plug in the initial state S0 and S0 is sampled from the initial distribution P0。Okay。

 so this value is by definition this。 So this is merely changing our notation。

 So in the expectation above， we only sample the initial distribution in this bottom expectation。

 the expectation below， we sample an entire trajectory， but within the entire trajectory。

 we only use the initial state as 0。Next， what we do is we write this V as a difference between these two summations。

 Now， if you pay attention to the summation index indices。

 the equality that's being claimed is actually quite trivial because this summation starts at t equals 0。

 So that's gamma to the power of 0 from v at s0 and a bunch of terms。

 And then here this summation starts at t equals1。 So really all the terms from t equals 1 to t big t minus-1。

 they all cancel out。 The only term that remains is v evaluated at s0。 So okay， I mean。

 we'll see why we did this a difference in summation。

 but the step here is mechanically speaking immediately verifiable。Okay。

 next what we'll do is we'll take this summation and we'll combine it into a single summation。

To do so we'llment decrement this summation index。 We'll have t goes from summation t equals0 to t minus2。

 and then we'll increment this t to t plus1 S to S t plus1。

 And then we'll note that here we have a minus sign And here with a minus1 so that cancels out that becomes a plus here and then here this term goes to here Okay so if we examine this initial term that's just straight up over here right so this is v at S t gamma to the power t summation string from t to 0 to t minus1。

 And then for this term we pull out a factor of gamma。

 So gamma to the power t plus1 is gamma to the power t times gamma So that's fine。

 And then V at T that becomes this index little t was incremented to s t plus1。

 So that goes over here。 The summationian index for this term should be from t equals0 to t big t minus2 because we decremented this thing。

 So this term has one additional term。 But what's that one。Additional term。 Well。

 the one additional term is if we consider the final term over here。

 we have big t minus1 we plug that in， so that will be the value function evaluated evaluated at S T。

 Now S big T is the terminal state because that's what defines big T and if you evaluate the value function at the terminal state By definition。

 the value function at the terminal state is0。 So the additional term that is present within this first part。

 that is additional single term is just0。 So it's okay for us to add that in and it doesn't make a difference。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_4.png)

Okay， so we've changed this second term into this thing and we've talked about that。

 Now this first a J0， a J theta that becomes this。 Now， if we examine this will J theta。

 that's our cumulative expected cumulative discounted return。 So we have the discounting。

 this is the cumulative discounted returns。 and the trajectory tau is sampled with respect to policy pi theta。

 So we're just applying the definition here。Now， one technicality that I want to point out is that here the expectation is with respect to theta pi theta。

 whereas here the terms are with respect to the policy pi theta 0。

 Now let's go back to where this all started Here we had the expectation with respect to the initial state of v pi theta 0 here we had pi theta 0 and we have to plug in the initial state Now the initial state is just the initial state is sampled from p0 so it really doesn't matter what kind of policy that we're using to generate the entire trajectory within this expectation but for reasons that we will see soon to make things work out later。

 we will have this expectation be generated be with respect to a trajectory generated by pi theta pi theta rather than pi theta 0 but that doesn't matter because the only state that's being used here is just state0 and the distribution of state0 is independent of whatever policy that we use。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_6.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_7.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_8.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_9.png)

But then within this expectation and within this expectation where we have the subsequent states being used。

 state 1， state 2， state 3， and so on， and so forth。

 that does depend on what policy pi that we're using。

 and those states will be generated by policy pi theta rather than pi theta 0。

So that that's a subtle point。 But in any case， because this expectation and this expectation is with respect to the same distribution。

 Both expectations are with respect to the trajectory tau being generated with respect to the policy pi theta。

 we can combine those two expectations and just write it in this way。 So we have this sum。

 we have this sum， we combine it and we get this thing。Now。

 if we take this term R plus gamma v with S plus1 plugged in。

 if we consider the conditional expectation of this term conditioned on the current state ST。

 the current action 8， then this comes out to be the Q function conditioned on ST and A。Okay。

 and finally， we recognize that this Q and this V that that difference is by definition the advantage function with respect to the policy pi theta 0。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_11.png)

Okay， so rewriting so this is what we've proven in the previous slide， so so rewriting this。

 let's continue with our calculations。😊，So let's start by isolating the initial terms so t equals zero term from this sumation。

 we just pull that out and then everything goes here just just the same thing。

 but here in the outer expectation let's consider the outer expectation with respect to the initial state and the initial actions so as you run a0 and then within the remaining terms let's have do the conditioning where we condition on the initial state initial action and then we take the expectation for the subsequent states and actions。

Next let's to the importance sampling estimator。 So when we change the distribution of a0 from pi theta to pi theta0 pi theta not and I'm using a different letter to denote the three random variable so a0 has distribution pi theta a0 prime has distribution pi theta 0。

 when we change the distribution， then we need to compensate for the change of distribution via this likelihood ratio。

 but instead of a0， we now plug in a 0 prime into here。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_13.png)

To verify that this holds with equality， what you can do is you can write this expectation with respect to the distributions pi theta pi theta 0。

 just write it as a summation， and you will see that the pi theta 0 cancels out with a pi theta 0 and youll recover this expectation。

So this step performed the important sampling change of distribution on the initial action a0。

 we can do the same with all the subsequent actions。

 so by repeating this argument we eventually arrive at the summation gamma to the power t with times this importance importance weight times the advantage function and now all of the actions are generated from distribution pi theta 0。

Now， this is kind of a funny expectation So to explain this expectation fully。

 imagine the trajectory tau。Grated by policy pi theta。 Now。

 this trajectory will generate a sequence of states and actions。 And let's only consider the states。

 Okay， so this trajectory has a sequence of states。

 And then as we visit a bunch of all of these states as 0 S1 S2。

 it will in order for the trajectory to be generated。

 we will be generating the actions a T in accordance to policy pi theta。 But at the same time。

 let's have another policy pi theta0， generate the action a prime T。

 Now this a prime T action is not going to affect the trajectory。

 It's just these actions that are kind of like imagine them just being proposed by this additional policy。

 we don't act on it。 But these additional actions A Ts a primes are just proposed by this additional policy pi theta 0。

 But eventually the transitions are done with the actions A。

 which are sampled in accordance to policy pi theta， but the actions A prime and T are just proposed。

As we sort of move along the trajectories and what we're doing here is we're taking the expectation with respect to these a prime actions which are proposed but not used in the generation in the trajectory。

Okay， so that was a somewhat elaborate derivation， but the conclusion that we arrive at is that the J objective function is equal to this expectation plus some constant C。

😊，Now， there is one final change that we have to make， and that is this theta here。

So what we want to do is we want to perform an optimization with respect to the parameter theta。

 We want to maximize the objective function J。 But when you do stochastic optimization。

 you usually want the optimization parameter to be within the expectation。 And so this present。

 this theta being present here。 That's fine。 But this theta being present on the definition of the expectation。

 that's usually undesirable。So this presence of theta here is a bit inconvenient。

 So what we'll do is we'll just simply replace this theta with theta 0。Now。

 let's define this function with the theta replaced with theta 0 as k theta centered about to theta 0。

Now theta， when theta is close to theta0， well， I mean this should be mostly the same right。

 so so j should be a good approximation， a k theta theta0 should be a good approximation of j theta for theta close to theta0 here when I say approximately to equal is I'm not really taking account to the precise value of c。

 but that's fine because C is represents a constant independent of theta and we're trying to optimize with respect to theta so the constant C is irrelevant。

So the approximation argument here is can be made a little bit more formal and it can be shown that J and K agree up to first order。

 So they are equal within a small neighborhood around a theta 0 up to first order。

 the gradients are the same， although the second order derivatives are not the same。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_15.png)

But the fact that the high order information， the second order and high order gradient information do not match is a little bit unsatisfying。

 so this approximation theoretically speaking is a little bit unsatisfying at least it is unsatisfying to me because the whole motivation was that we want to extract more information from our samples beyond the mere gradients now K and J agree up to first order。

 so the gradients of J and K are equal， but if we want the K to be a good surrogate of J in a way that allows us to extract more information than just the mere gradients。

 then one might argue that we need more something beyond just first order agreement we might want the surrogate objective function K to agree with J up to the high order derivatives。

 something like that， but in any case， at least K and J they do agree up to first order within a neighborhood that theoretically that might not be sufficient。

To convince one that k is a good surrogate， but at least it's equal to first order and that's perhaps the bare minimum and empirically speaking。

 the use of k people have tried using it and it works pretty well as we will see soon。Okay。

 so we're going to use K as a surrogate objective for J。And the way we'll do it is。

 well a K is still defined with an expectation。 So we need to somehow approximate this in a way that we can use。

 So what we will do is we'll sample Iid trajectories trajectory tau1 up to tau n。

 so we'll sample n trajectories。😊，And we'll just perform an empirical average。

 So we pick an average over n trajectories， and we just plug in the trajectory values into here。

And here， a hat is going to be some sort of advantage estimate which we will specify。

 which a specific form will specify later on。Now， this approximation is going to be accurate when n is large right by the law of large numbers。

 when n is sufficiently large， the expectation should be the same as the finite sample should approximate the expectation pretty well。

 But there's actually one additional requirement。 So an additional requirement is that we need pi theta to be sufficiently close to pi theta 0。

 And more generally speaking， here we're doing important sampling where we replace the distribution from pi theta to pi theta 0 when we when we're using considering the distribution of A。

And this kind of important sampling estimator， they become inaccurate when the sampling distribution of pi theta 0 is too far away from the nominal distribution pi theta。

Okay， so we're going to use use the surrogate objective。

 We're going to maximize the surrogate objective， but we will subject the optimization to a certain trust region constraint。

 The optimization looks like this。 So we maximize this empirical average of the surrogate objective。

 but we will subject our optimization to the constraint that the theta should be in some sense close to the distribution that the parameter of theta 0 to clarify again。

 this trust region constraint is needed for two region reasons。

 One is that the surrogate objective by its derivation is only meant to approximate J well when theta is close to theta 0 and also because of the discussion of this right so this can only be accurate when the sampling distribution pi theta 0 is sufficiently close to the nominal distribution pi theta。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_17.png)

So that leads to the reinforcement learning algorithm TRPO TrRPO is the abbreviation of trust region policy optimization。

 and this solves a sequence of trust region optimization problems to improve the policy and the trust region is defined by the k divergences of the policy Okay。

 so let's read through the algorithm So the whole thing is enclosed within a while loop at the beginning。

 we sample an independent trajectories from our current distribution。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_19.png)

And then we have this surrogate objective and for the sake of simplicity， notational simplicity。

 I just remove the one over n factor， the one over n doesn't affect the objective because it's a constant factor。

Now here is the trust region constraint so the trust region constraint instantiates the requirement that the optimization variable theta must be close to the sampling distribution theta current so and the way it does it is it says that the k divergence of the distribution defined by pi theta should be close to the distribution defined by pi theta current and that makes a lot of sense because theta is just the neural network parameter so it doesn't really make that much sense to say that theta next should be close to theta current in the sense of let's say mean squared error the purpose of theta is to define the policy pi so here this trust region constraint is saying that the distribution defined by pi should be similar the distribution defined by pi theta next should be similar to the distribution defined by pi theta current and that's conceptually more in line with with what we actually want。

Okay， so we solve this optimization problem then that and once we solve it， we perform。

 we update the parameter。And then what we do is we compute the cumulative discounted returns at every time step。

 and then we use that to fit the value network。And then once that is done。

 we move on to the next iteration and then we sample again n trajectories。

 But this time the theta has been updated。 so we have this sort of repeating process where we sample trajectories from the current policy pi theta current and then we solve this trust region constrained optimization problem to update the policy parameter theta so we are looping through this process where we generate many trajectories and trajectories。

 then we perform the optimization， the trust region constrained optimization and it's constrained in a way that we aren't allowed to move away too much from our current policy parameter。

 but we make some updates and we commit to that change and then in the next iteration。

 we sample additional and more trajectories now with the updated parameter and then we perform the maxim to determine our next policy parameter。

 so on and so forth。

![](img/294d57c980c5d60a2c8cbbc42365d5aa_21.png)

Now， when you compute the advantage estimate， the advantage estimate can use the value network。

 So here we have this value network as the baseline function。

 and that's why we need to be continually updating the value network alongside the policy network as well。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_23.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_24.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_25.png)

Now here I'm just saying we should solve this maximization problem Now a lot is actually hidden away behind this word solve。

 So in the original TrRPO paper referenced over here。

 they actually use some sort of approximate newton method which resembles a natural gradient method given the presence of the kdirgence penalty and with an approximate newton method you need to solve the linear system H inverse times G where G is some sort of approximation of the Hessian matrix。

 and this is solved with via the conjugate gradient method。

 so I'm actually going to skip over the details because that's actually quite a handful of material from numerical linear algebra and numerical optimization。

 and it's used to a good effect in the TrPO algorithm but the subsequent developments aim to avoid these kind of complications。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_27.png)

So the problem with a TrRPO is that implementing it is hard work due to the trust region formulation。

 you need to understand what con graded is。 you only need to understand these approximate new to methods it's a lot of sort of background material one needs to understand and it's not just the requirement of the human user learning new material it's also unclear whether this second order optimization formulation is efficient So TrRPO of again。

 these approximate new to method formulation well the new to method is a second order optimization method and the idea that you want to in a second order optimization method。

 you use the second order derivatives of the function but this is not what most deep learning optimizations do in most modern deep learning formulations things are neural networks are optimized via first order optimization algorithm So things like stochastic gradient and descent where you take the gradient you move in the negative gradient direction and you don't ever utilize second order information。

So you don't ever utilize explicitly utilize second order derivatives or your neural networks in most modern deep learning formulations。

So the proxima policy optimization PPO， this approach returns to the first order of formulation while keeping the trust region idea。

If you read the original PPO paper， which is referenced over here。

 the PPO paper presents two algorithms， PPO penalty and what they call PPO C what we're going to talk about in this lecture is the PPO C algorithm because thats what that is the algorithm that people nowadays use when people say a PPO PPO penalty is not really used commonly nowadays。

Okay， so PPO uses what's called the clipped surrogate objective。

So the clipped surrogate objective of PPO has this form。

 so here this C function as parameterized by epsilon takes it as a but the likelihood ratio and an advantage estimate a had and let's define it in this piecewise way。

Now the equations behind this defining this clipped surrogate objective。

 they might look a little bit cumbersome， but this clipped PPO objective。

 this is what powers a lot of modern deep reinforcement learning and also most of reinforcement reinforcement learning on large language model。

 so let's go through all of the details of this clipped surrogate PPO objective。Okay。

 so this clips PPO objective， one way to define it is define it in a piecewise way。

 when the advantage estimate is positive or0， then the objective is defined as the minimum of the likely ratio comma1 plus epsilon。

Now， and then when the advantage estimate is negative。

 then as the maximum of the likelihood ratio comma 1 minus epsilon。Now here is the interpretation。

 let's think about the interpretation。Okay， so in our policy gradient methods。

 when the advantage estimate is positive， we want to make that action more likely。

 So when the advantage estimate is positive， we want to make this likely at ratio because we want to make this probability larger。

😊，So when the advantage estimate is positive， we want to increase this likelihood ratio。

 But what this clipped surrogate objective is doing is that， yes， we can。

 and we should increase the subject。 But we can we should increase it only by a factor of one plus epsilon。

 So remember， theta starts out is initialized at this theta K in this case。 So initially。

 this likelihood ratio is one。 And through the training， we want to increase this likelihood ratio。

 but we're only allowed to increase it up to one plus epsilon。 And thereafter， in the training。 Yes。

 we might still increase this likelihood ratio。 There's nothing stopping us from doing it。

 but we're no longer provided the incentive to increase the likelihood ratio beyond one plus epsilon。

 So the objective rewards us from increasing this likelihood ratio up to one plus epsilon。

 but not any further。😊，When the advantage estimate is negative， that means that's a bad action。

 So we want to reduce this likelihood ratio。 again， at the beginning of the training。

 beginning of this inner loop of training， this likelihood ratio is one， and we want to decrease it。

 and we can decrease it up to factor 1 minus epsilon， which is a decrease。

But there is no further incentive to decrease this likelihood ratio beyond one minus epsilon。

 We can reduce it。 Sometimes it does get reduced beyond one minus epsilon。

 but there's no incentive to do so。So this clipped PPO objective。

 it basically removes the incentive to change theta too far away from theta K。

 basically whether the advantage is positive or negative， we can move it up a little bit。

 move it down a little bit and that's some amount of change but once we max that once we saturate that gain。

 then there's no further objective， so the effect of using this clipped surrogate objective is the parameter theta does not is not optimize away from the starting point base point theta K too much。

By the way， this clipped PP objective can be equivalently written as this min of this thing。

 So we have a minimum of these two qualities， and this clip is just the projection onto the interval one plus epsilon1 minus epsilon。

 The fact that this definition and this definition is equivalent is something that can be just worked out。

 So you sit down and you work out some of the terms and within a few minutes。

 you can show that these two are equivalent。 I won't go through the derivation myself because there's not too much insight beyond the sort of mechanical derivations。

 but again， these two are equivalent。 The way I understand the way I sort of into it about the PP objective。

 I think is the clipped PP objective is better captured in this initial definition。

 So that's why I'm showing you this definition first， I think this captures the intuition better。

 But in most publications， people will elect to write this objective。 So in papers。

 you'll recognize this version of the the clipped surrogate objective expressed in this way。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_29.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_30.png)

はい。So that leads to PPO so in TrRPO we solve a constrained optimization problem。

 a trust region constrained optimization problem， but in PPO this is what the algorithm looks like so we sample and trajectories from our current policy and then we solve this optimization problem with now with the clipped objective and no constrained and that's much more convenient because now that we don't have any constraints we can just simply use first sort of optimization algorithms to solve this maxim problem more specifically this optimization is like。

More specifically， if this optimization sub problem is solved with methods like schastic gradient descent or atom。

 but one additional detail to point out is that it's done with early stopping。

 So this inter maximization problem is not solved until convergence。

 It's solved you only do a limited number of SD or atom iterationations。

 and that's because the trust region constraint is implicitly enforced by clipping。 And again。

 I explained that we。And again， we discussed the fact that the PPO clip objective。

 it removes the incentive to optimize the parameter theta too much。 but still。

 if you do optimize this to completion that sometimes moves the parameter theta away too much。

 So by limiting the number of Sgd iterations， but only performing a few SGD iterations。

 we are able to maintain theta to be within the vicinity of the current value of theta much better。

 So the trust region constrained is really implicitly enforced by two mechanisms。

 One is the clipping mechanism and one is the SD early stopping mechanism。😊。

So after this maximization problem is solved approximately。

 then we update the current parameter to be the result of this optimization problem。

 and then we go on to compute the target function to fit the value network。But by the way。

 the choice of the advantage estimate there's more than one possible choice。

 one thing that people use is the GAE estimator， I'll talk about that soon。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_32.png)

In the initial PPO paper， the clipping parameter was set to be epsilon is 0。2。

 and it seems like this value of 0。2 is still commonly used。

 although in modern reinforcement learning of large language models。

 people things a little bit differently， sometimes they use a different value of epsilon for the upper and lower clipping。

 but in any case as a rule of thumb something like 0。

2 is a reasonable value for the clipping parameter。In the maximization objective。

 we have this double summation。So going back here， this is the double summation that I'm referring to in the maximization objective。

This can be viewed as a loss formed with n times t data points。

 so there are n trajectories and t is the trajectory length for the n trajectories。

When you perform the maximization， you often perform something like 10 epochs over the N T data points。

 so I said you do SGD or atom with early stopping， so how early。

 well by early I mean you perform something like 10 epochs over these data points。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_34.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_35.png)

Strictly speaking， TrRPO and PPO are not policy gradient methods because， well。

 if you look at the objective， the objective is design as an improvement beyond the policy gradient method of the A3C method。

 but it doesn't explicitly involve a gradient， but nevertheless I think it's reasonable to consider a TrPO and PPO as variance or enhancements of the deep policy gradient methods。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_37.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_38.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_39.png)

In the PPO algorithm， we need to use the advantage estimate a hat。

 So if you go back to the algorithm here， the advantage estimate a hat is being used in PPO here I didn't in this slide。

 I didn't discuss the specific choice of a hat， so let's discuss the specific choice。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_41.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_42.png)

Let's assume for the sake of argument that we know that we have access to the exact value function for the current policy pi current。

 Then it is a relatively straightforward exercise to show that all these TD estimate。

 So this is the TD1 estimate。 So we have we get the current reward the current reward and we transition to state S plus1 and S plus1 and we plug that into the current value function。

 and we subtract out as a baseline， the value function evaluated at the current state S。 This is TD1。

 we have a TDk。 So we considered k transition。 So at the current state S。

 were at the current we start this current state S and as a baseline。

 we subtract out the value function at the current state S。 But then we perform k transition。

 So we get reward Rt Rt plus1 up to reward R T K T plus k minus1。

 and then we transition to the state T plus k。 and then we plug that state into the true value function。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_44.png)

V pi current。 and then we also incorporate the discounting。 So this is TDK。

 and let's consider TD infinity。 Well TD infinity is just basically the Monte Carlo estimate minus the baseline function。

 So here just we have the the full cumulative discount in return minus the baseline function。

 So the value network value function evaluated at the current state S。

It's a relatively straightforward exercise to show that these all share the same mean。

But they have different variances， and the different variances can be explained by the Ra black wall theorem。

 So as K becomes smaller， you have a smaller variance。 So to restate the claim， all of these。

 the TDk for K starting at 0 and going up to infinity， they all。

 if you take the conditional expectation with respect to the current state and the current action conditional on the current state and the current action。

 you get the advantage function on the current state and the current action。 This is a typo。

 that should be。This should be our AT。And the claim that the variances are different is， well。

 the TD1estator has a smallest variance variance， TDK has a larger variance and TD infinity has the largest variance。

Again， this variance this sort of sequence of different variances。

 this can be understood via the real blackwell theorem。

 or it could be understood more intuitively based on the following logic。 So for TD1。

 you have the randomness in R T and then S plus1。 So this contributes to the randomness。 But for TDk。

 you have many more rewards。 and you transition to S T plus K。

 and this is a transition farther down the line。 So there's more randomness。 And then at TD infinity。

 you have more rewards that's being added。 And so that's more randomness。

 and the more randomness you have the larger the variance。😊，Now， in practice， of course。

 we do not have access to the true value function， so the use of the value function is replaced with the value network。

 So this is the actual advantage estimates， the TD advantage estimates that can be used in practice。

Now these TD estimators are actually no longer unbiased for any finite value of k。

 So if you consider the conditional expectation of the TD estimator， you can show that。

 well you have the current the true Q function， minus the baseline function。

 but the baseline is not the true value function is the value network。

 but that's okay because in the policy gradient derivation。

 value the baseline function doesn't actually contribute to the expectation。

 it only contributes to the variance。 So when we're talking about the unbiased this property。

 the fact that this is not v pi and that it is v phi， it's fine but this term is problematic。

 So you have this additional term which is bias and this bias is proportional to gamma to the power1。

If you can take the conditional expectation of the TDK advantage estimate。

 condition on the current state STN， the current action A。Then you get the same thing here。

 but you have this additional you have this bias term。

 and this bias term is actually smaller because this one's proportional to gamma to the power T and if gamma is a discount factor strictly less than1。

 then gamma to the power K is smaller than gamma so this becomes a smaller bias。

And then for TD infinity， the Monte Carlo estimator， we don't have any bias here。

 So this becomes an unbiased estimator。 Again， this is not v pi。 It's v phi。

 but this baseline function doesn't contribute to the expectation to the app mean in the policy gradient sense。

 So this discrepancy is fine。When we're using the actual advantage estimator where we use the value network。

 it's difficult to have a precise analysis of the variances。

But we still expect the variance to be an increasing function of K。

 So we expect that a hat of TD1 to be the smallest A hat of TD2 to be TD K to be intermediate and the a hat of TD infinity to be the largest。

So we now have a bias variance trade off with k。 So when K is small。

 our advantage estimate will be will have large bias， but small variance。 And then when k is large。

 our advantage estimate will be have small bias， but large variances。

But what about the dependency on gamma， Well， let's consider this setting where maybe we even consider an undiscounted MDP。

 but we will still use an artificial discount factor for the sake of controlling the variance。

 So if we think of gamma as an artificial discount factor。

 then it's a parameter that we choose in our optimization algorithm in our learning in our reinforcement learning algorithm。

 And then in terms of expectations， if the base MP that we're considering is an undiscounted MP。

 then gamma equals one is the correct choice。 So if k is infinity and gamma is equal to one。

 then we have an unbiased estimator。 And then using a smaller value of gamma。

 an artificial discount factor that introduceds bias。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_46.png)

However， with gamut less than1， the later rewards， let's say， no。

 in this K step TD estimator this reward is proportional to gamma proportional to gamma to the power K minus-1。

 and this is well smaller than one。 so the later rewards contribute less and therefore since they contribute less in the summation。

 they also contribute less to the variance。So we now have a bias varianceance trade off with respect to the artificial discount factor of gamma when gamma is small。

 we have a large bias， but small variance， and when gamma is large and we have a small bias。

 but we have a larger variance。Okay， so now in choosing our advantage estimate。

 our TD advantage estimate， we have two hyperparameters to choose。

 One is the artificial discount factor gamma， and then the other is the TD step K and for a gamma and K。

 we sort of mapped out what is the trade off， the biospherous tradeoff in this choice。

And gamma is a nice parameter， it's a continuous variable so we can tune it to be whatever we want。

 but one thing about k is that K is a discrete parameter。

 and that makes it a little bit more difficult to tune。So one challenge with2 K is that it's again。

 a discrete parameter can be continuously tuned， so maybe you want to try something that's between4 and 5。

 but you can't do that。 Well so the generalized advantage estimation GAe。

 this uses an exponentially weighted average of all of the TDK estimators based on an approach that is analogous to the classical technique called TD Lambda So TD Lada is an idea that comes from classical reinforcement learning。

Alright， so let me explain what GA actually does。 So let's say we're given a function V。

 V is a function of the state S。 So this is meant to approximate the value function， v pi of s。

 let's define this notation V Dlta V T。 Okay， so Delta V T。

 that's the that's the one step Td estimator， right。

 So reward plus gamma v to the of the sub sequence step step minus the value function evaluated at the current state。

Then we can actually， interestingly， we can express。

The TDK estimator as a discounted sum of these deltas。

 And this follows just from a telescoping sum argument。

So I won't write out this precise telescoping some argument。

 but I encourage you to pull out a piece of paper and write out the argument。

 and you'll see pretty quickly that， yes， indeed the TDK advantage estimate can be written in this way。

Okay， so here is the definition of the GAE estimator。

 The GAE estimator is defined for lambda between0 and 1 in this way。 So note that， well。

 we have a sum of TD1， TD2， TD3 and it's weighted in an appropriate way and it turns out you through a geometric sum argument we can write it in this way where now this GaE estimator is again。

 a discounted sum of all the deltas but the discounting is done in a different way。

 discounting is done in a more aggressive way for the TDk estimator。

 we had a discount factor of gamma and then when k becomes infinity than the summation goes all the way to infinity。

 but in the GE estimator， this sum goes infinity， but we have a smaller discount factor。

 gamma times lambda， and this is smaller because lambda is a value between a0 and1。Now to clarify。

 when gamma is equal to0， then here this front factor this just becomes one and all the subsequent stuff that's just0。

 So we recover the Td1 estimator when gamma is equal to1。

 then you can't just plug in gamma equal to1， but you can do some sort of limiting argument to show that the GAE estimator becomes the TD infinity estimator so when gamma is equal to one。

 you take the limit as gamma goes to1 and it makes sense。

So here I'm rewriting the identities and the definition that I've stated in the previous slide。

 so here this is the definition of the delta VT quantities that this was defined in the previous slide here I made the assertion that through the telescoping sum argument we can write the TDK estimators as a discounted sum of these deltas and the GAE advantage estimator is defined in this way and it can be shown through a geometric sum argument that this sum can be written as a discounted sum of the deltas。

Again， when lambda is equal to 0， the GAE estimator recovers the TD1 estimator。

 and when Lada is equal to1， the GAE estimator recovers the TD infinity estimator。

Now if it is the case that this value network is equal to the true value function。

 then the GaE estimator becomes an unbiased estimator。

 so I'll leave it as an exercise to show that this delta delta V t quantity the expectation of that condition on st and8 that's equal to the true advantage function。

 and then the subsequent delta so delta v of t plus L where L is bigger than1 that conditional expectation it turns out to be0 so we can show with this identities we can show that when V is equal to the true value function。

 the expectation of the GE estimator condition on st and8 well we're going to use this identity。

 So we have this transformation the first term will yield the conditional expectation will yield the advantage function。

 the true advantage function， and the remaining terms will just contribute to zero mean so we will get the advantage function in the end。

That makes the GAE an unbiased estimator， again， when the value network is equal to the true value function。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_48.png)

So okay， so then what's the bias variance trade off of the GAE estimator here Im again。

 I'm rewriting the GAE estimator。 This is the definition。 and this identity again。

 I claim that it can be shown using a geometric sum argument。

So the lambda parameter of the GAE estimator is a continuous parameter。

 and it serves a similar role as the K parameter of the TD estimator。

So when the value network that's being used is equal to the true value function。

 then any value of lambda incurs no bias， as we've just discussed in the previous slide。

 this is different from gamma。 So unlike gamma。 So when gamma is strictly less than one。

 we always incur a bias， no matter whether whether or not the true the value network is equal to the value function。

 But when the value network is not equal to the value function， which is of course。

 a case in practice。 then a large choice of lambda。 So lambda close to one。

 it allows the telescoping structure to reduce the bias。 and and furthermore， in the extreme case。

 where lambda is equal to one and gamma is equal to one。 So in that case。

 you're not really using the GE estimator using the undiscounted td infinity estimator。

 but in this extreme case， there is actually no bias。 So you get an unbiased estimator。

 But if you use a smaller value of lambda than the bias becomes larger。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_50.png)

So here so now to summarize， here's the bias variance trade off with lambda and gamma。

 So if you use a small gamma that's large bias， but smaller variances with large gamma。

 that's smaller bias， but larger variance。 and by large gamma， I mean a gamma that is close to one。

Similarly， for Lada， for the GAE estimator， a small value of Lada that incurs a large bias but small variance and a large lambda。

 so lambda close to one， that incurs a smaller bias but a larger variance。

When people use TRPO and PPO， the GAE estimator is commonly used as the advantage estimator。

 although some TDK estimator or TD1 or TD infinity or TDK， those are also valid choices。

 but the GAE estimator is used commonly and a common choice of the GAE parameters is gamma equals 0。

995 and lambda equals 0。96 and the choice of lambda being smaller than the value of a gamma there's a sufficient empirical as evidence justifying that。

Okay， so so far， we've talked about T RRPO and PPO。

 and we derived TrRPO and PPO as enhancements of the policy deep policy gradient method。

 and this derivation closely mirrors the derivation that was presented in the original T RRPO paper。

 However， I would like to also talk about an alternate interpretation of these two methods， namely。

 that we can interpret TrRPO and PPO as approximate policy durations。

To do so let's first define the notion of a policy advantage。

 so we define the policy advantage of policy pi over a current policy pi k in this way。

 so we'll denote the advantage the policy advantage as I because we can't use a is the usual advantage so let's define this notion I as a function of pi based on around pi k and this is the definition。

 so we have sum of the advantages discounted some of discounted advantages where the advantage is defined with respect to the policy pi k and then we take this expectation where we follow a trajectory tau generated by policy pi k but into the advantage function。

 we feed in the states s that are that's part of the trajectory tau。

 so the states S are generated in accordance to policy pi k。

The actions are generated in accordance to the policy pi。 So the actions here we write it as a prime。

 and those are generated in accordance to policy pi。

So let's let me give you an interpretation of this。 So what we'll do is within the expectation。

 we'll follow a trajectory tau generated by pi K as stated over here。

 But as we follow the trajectory tau， we ask what actions the other policy of pi would have chosen。

The policy advantage quantifies how better as measured by the advantage function with respect to pi k。

 these actions are compared to the actions chosen by pi k， So again。

 to sort of repeat this interpretation， we're going to follow a trajectory tau tau is generated by pi k。

 but as we follow the trajectory tau， we will observe a bunch of states。

 and the policy pi k will then choose an action to continue the trajectory。

 but as we visit these states， policy pi k will choose an action， but we will also ask on the side。

 policy pi and well ask what actions would you have chosen， We're not going to follow those actions。

 We're going to follow the actions as chosen by pi k， but dear policy pi what would you have chosen。

So then the actions that pi K chooses and the actions that pi choose will have different distributions。

And then we feed that action chosen by policy pi into the advantage function。

 and the advantage function might come out positive might come out negative， but in expectation。

 it will quantify how better are the actions of pi compared to those actions that pi k would have chosen。

So that's the interpretation of the policy advantage I pi given pi k。

 Now note that if we plug in I pi k of pi k， so if we plug in pi is equal to pi k well。

 that's just zero now intuitively that's sort of that's quite natural because we follow policy pi k and then we ask the same policy of pi k what action when you have chosen and then are those actions any better compared to the action that well pi k shows well。

 I mean its the same distribution of actions So theres the actions chosen by pi k of equal quality as a policy as the action chosen by the same policy pi k so this ought to be equal to0 and if we examine that this definition this expectation。

 well the advantage function has zero expectation the expectation of the advantage function is zero sort of by definition if the action is chosen in accordance to this policy pi k。

And that follows from the fact that the advantage is defined as a Q minus v and the expectation of Q。

 if you choose the action according to the same policy， the expectation of Q becomes V。

 So you have v minus v， and that becomes 0。Okay， so here's an important property of the policy advantage。

 So a policy pi K is an optimal policy。 if and only if the maximum of the policy advantage is equal to 0。

 Now， let's interpret this more， more carefully so。

You can always plug in pi is equal to pi k and attain a policy advantage of 0。

 So what this max is saying is that， yes， you can always plug in pi is equal to pi k and get a value 0。

 So then max over pi that being equal to 0 means there's no way to improve the policy advantage beyond plugging into pi k itself。

 So the maximum is attained at pi k pi equals to pi k attains this advantage this maximum。

And intuitively， this makes a lot of sense because the policy advantage is indeed a measure of how advantageous this policy pi is compared to pi K。

 So if no other policy has an advantage over your current policy。

 then that means your current policy is optimal。Now it turns out the classical policy iteration can be expressed as maximizing the policy advantage so here again I'm just repeating this is just repeating the definition of the policy advantage I and my claim is that policy iteration can be written in this way so this one line description of the algorithm is at iteration K we have policy pi k we maximize the policy advantage over all policy pi and that yields a subsequent policy pi k plus1 and this is policy iteration。

So strictly speaking， there's a technicality behind this equivalence。

 the equivalence does require that the trajectories generated by the policies PK， they have。

 the requirement is that they have positive visitation probability for all states。

 but let's not dwell on this technicality。Okay， so then here's the quick proof。

 The policy advantage I is maximized if there is a policy of pi that maximizes these advantage functions individually within the sum summation within the expectation。

 if the policy maximize these advantage functions individually for all possible states S then that that policy pi would maximize this expectation。

 it would maximize this policy advantage and we can choose such a policy so we choose a policy of pi to be the agon max of the advantage function with respect to policy of pi K for any given s and maximize with respect to the action A。

But if you think about it， this is actually exactly equal to policy iteration。

 because if you remember what the advantage function is， the advantage function is Q minus V。

But within the two terms Q and V， only the Q function depends on the action A。

 So agon max of a is actually the same as agon max of Q。 So choosing pi as agon max of Q pi K。

 If you remember what policy iteration is that is exactly the definition of policy iteration。

 So policy advantage maximization is equivalent to policy iteration。Okay。

 so then let's think about performing this policy advantage maximization， which is equivalent to。

 of course， policy iteration。So in practice， the expectation of the policy advantage has no closed form formula。

 we can exactly evaluate it when the number of states and actions are small。

 but we're not considering that set setting， we're considering the setting where the number of states and actions are large so this expectation now this policy advantage has no closed form formula。

 so we will have to approximate it with important sampling estimates。😊。

The way we do this do this is we sample a trajectors tau1 up to tau n。

And these are I as I trajectories。 And we form the estimator I had。 So recall， this is the， again。

 the definition of the policy advantage。 I'm just rewriting the definition right over here。 Now。

 let's' rewrite this using these importance sample likelihood ratio。

 So instead of sampling the a actions from policy pi。

 I'm going to sample the actions from policy pi K。 So that changes the distribution of the policies the actions from pi to pi K。

 So in order to compensate for that， we need to put in this likelihood ratio。 Okay。

 so this holds with equality。 Now I'm going to sample n Iid trajectories and I'll form this importance sampling estimate where this summation is going to to approximate this expectation。

This estimator is going to require the use of some advantage estimator。

 The advantage estimate needs to satisfy this condition， and these can be the TD advantage estimate。

 or this can be the GAE estimator。So when n is large。

 we expect that I hat should be a good enough approximation of the policy advantage I， right？



![](img/294d57c980c5d60a2c8cbbc42365d5aa_52.png)

So we can now interpret TRPO or PPO as an approximate policy iteration or an approximate policy advantage maximization。

 Let's consider this approximate policy iteration form， So here we sample n II trajectories。

 we form this finite sum estimation of I hat I as I we call that I hat and then using this i hat we perform the policy maximization。

 but this is deep reinforcement learning， so we don't maximize with respect to the policy directly we have a parameterized policy parameter with a neural network and we maximize the policy with respect to the neural network parameter theta。

 So this am is computed approximatelyly using things like using the usual optimizes like atom SGD。

 things like that。

![](img/294d57c980c5d60a2c8cbbc42365d5aa_54.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_55.png)

Now， if we were to do this， this version of approximatema policy iteration would fail。

 this fails because this approximation I had been close to I。

 this requires that these two distributions pi theta K and pi theta K plus1。

 it requires that these two distributions are not too different。

 So this was discussed in our earlier derivation of TrRPO in general。

 if you have an important sampling estimator that it becomes inaccurate when the sampling distribution gets too far from the nominal distribution。

 therefore we need a trust region or some sort of proximal mechanism and this leads to TrRPO or PPO。

So that means we want to constrain this maximization such that pi theta and pi theta k are not too different。

 so a direct constraint using a k divergence will lead to TrRPO。

 and then using this clipping mechanism， the PPO clip objective and also a SD early stopping mechanism to indirectly prevent a pi theta K from optimizeimizing being optimized too far away from pi theta K that leads to PPO。

Okay， so TrRPO and PPO are good reinforced deep reinforcement learning methods。

 It had a huge impact on modern， deep reinforcement learning that has been used in a wide range of settings。

 It has also been used in the context of reinforcement learning on large language models specifically PPO has been used in reinforcement learning with human feedback。

 But there's one downside of these methods。 And that is that we must learn two neural networks pi theta and v phi。

 Now， in a reinforcement learning setting。 Well， the end goal is to learn the policy。

 we want to undergo the reinforcement learning and as an outcome。

 we need to be able to we want to be able to make good actions in the environment。

 and the policy is what allows us to make good actions。

 So it's reasonable to argue that the fact that we need to learn P theta should not be considered a problem。

 But what about V p。 Well， we have been referring to this V p function as a baseline function or a credit function。

 And this is an additional layer of。plexAnd it would be better if we can avoid it。Because after all。

 once the RL training is done， we're going to use the policy pi theta to use our learned agent。

 V Phi is not really going to be used once the the training is complete。

 So if we recall why V Phi was needed， Well， V Phi was used as a mechanism within the training and really only within training。

 So once training is done， V Phi is discarded， It's not really used。

 Why did we use V P to assign the appropriate sign plus or minus on our gradient signals。

But in our derivation of the policy graded method， we noted that the use of the baseline function is。

 in a certain sense， not mandatory。 So the baseline function serves the purpose of reducing the variance。

 but the baseline function doesn't affect the the mean of of the stochastic graded。

 So we could consider using PP PO without baseline。

 So let's consider this specific setting relevant to the reinforcement learning of large language models。

 So let's consider this undiscounted MP。 but we don't use a gammatry。 So gamma is one。

 There's no and there's no artificial gamma。 We assume a nonzero reward is collected only at the end of the episode。

 So so there are no intermediate rewards。 The episode episodes can terminate。

 And when the episode terminates， we get a reward。

![](img/294d57c980c5d60a2c8cbbc42365d5aa_57.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_58.png)

In this case， our TD infinity estimator is just the reward that we collect at the terminal time。

 so here， since there are no intermediate rewards， instead of writing assigning rewards to all the time steps。

 let's just assign the reward the total reward。Which we collect at the terminal time and let's just write that as R。

Okay， so then in this setting， a PPO without a baseline function， the algorithm will look like this。

So at every iteration， we sample N IID trajectories from our current policy。

 then we form the PPO clipped loss function and we maximize with respect to the parameter of theta and we'll do early stopping as we usually do and that's it。

 and then we update our policy parameter theta and in place of the advantage estimate we're not going to use the baseline function。

 So we'll just simply plug in the TD infinity Q estimate。 So that's just a reward。

 So here in place of the advantage estimate， we just plug in the terminal reward。Okay。

 so there are two elements that significantly simplifyimpl this PPO instance。

 One is that we're considering an undiscounted entityP。 So there's no gamma。

 and also we consider only a terminal reward。 So that greatly simplifies the PPO algorithm。

 But the other simplification is that we don't have a baseline。

 So we don't have to train the baseline。 We don't use the baseline。

 That significantly simplifies the PPO algorithm。But the problem with this algorithm is that it just won't work because without the baseline function。

 the variance of the objective will be too large， So this will either not work or even if it works。

 it'll be quite inefficient in terms of a sample efficiency。

 The training will take much longer compared to the version of PPO that does use the baseline。

So then this leads to the algorithm GRPO so we'll again consider the undiscounted MDP with no gamma trick and we's again assume we have nonze reward collected only at the end of the episode is so the same setting as in the previous slide。

Group relative policy optimization， GRPO。 This is a modern deep reinforcement learning algorithm proposed specifically for the reinforcement learning of large language models。

 And this replaces the baseline function with a batch norm style normalization of rewards。

 So here's the while loop， and we sample N Iidd trajectories。

 and let's write boldface R to denote the vector of the n terminal rewards。

 So we have N Id trajectories。 All of these will have some amount of terminal reward。

 Let's write boldface R to denote the vector of length N of these rewards。😊。

Then the only difference between GRPO and PPO is what we plug in here in the position of the advantage yesterday。

 so recall that in PPO we just plugged into terminal reward R。But instead of that。

 we're going to plug in a normalized reward。 So from this reward R。

 we will subtract out the mean and we'll divide by a standard deviation and we'll add a little bit small epsilon parameter just to ensure that we have that we never have division by0。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_60.png)

Okay， so then is this a good idea。 Well， let's think about the meaning of the advantage。

 The purpose of the advantage function is to measure how good is an action A T compared to the average action that would have been selected by the policy pi。

 given that we're at currently the state S T。Now， if you look at this GRPO socalled advantage estimate。

 what this does is this compares the current reward that you got。 you subtract out the mean。 Now。

 what does this mean， Well this is the average over multiple rewards obtained by this current policy So actually this mean is a reasonable baseline it gives you a reasonable baseline of what the average reward you can expect to collect if you were to follow the policy a pi。

And then you divide by a standard deviation for the sake of normalizing things。Now。

 this a so-called advantage estimate and I'm cautious when I'm using the word advantage estimate because this a hat is referred to as advantage estimates within many of the recent papers。

 but it is not an unbiased estimate of the actual advantage function。

 So I'm a bit uncomfortable referring to that this as an advantage estimate。 In any case。

 this a hat thing。 This does measure at least conceptually similar information compared to the true advantage function。

 So here's what the a hat measures。 So you have a trajectory that takes a sequence of actions。

 It yields a certain reward。 So how good of a reward is this compared to the other actions selected by policy pi。

 which yields these other rewards。By the way， this epsilon that's over here。

 this is something this is an epsilon that's reminiscent of the epsilon used， let's say batch norm。

 the deepse teams's Github repo uses epsilon is equal to 10 to minus-4。

 but by having this positive value of epsilon sometimes the rewards within a batch within your n trajectories they're all the same in which case you have zero standard deviation。

 So in that case the a hat quantity just becomes0 because in order for us the standard deviation to B0。

 then all of the rewards must equal the mean so the numerator becomes0。

 the denominator becomes epsilon so we have zero divided by epsilon So a hat is equal to0 and that results in a no updates。

 which makes a lot of sense because when the standard deviation of the rewards are0 that means all of the trajectories had equal reward。

 So they're all equally good so there's really no learning signal there so no updates should happen。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_62.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_63.png)

Oh， and I I also should clarify that there is this slight slight clash clash of notation。

 So this epsilon is to prevent division by 0。 And as I just said。

 think of this epsilon as something like 10 to the -4。 But this epsilon is the PPO clip。

 Epsilon and think of this as something like 0。2。 So this epsilon and this epsilon。

 These are different epsilons。😊。

![](img/294d57c980c5d60a2c8cbbc42365d5aa_65.png)

Now here are some caveats of the GRPO algorithm， so GRPO should not yet be considered a general deep RL method because its effectiveness has not been tested outside of the LLM applications。

 as far as I know， GRPO has been used in the reinforcement learning of LLMs。

 but not really in other RL applications。

![](img/294d57c980c5d60a2c8cbbc42365d5aa_67.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_68.png)

Also， I should clarify that GRPO is not the first modern deep R method that foregoes the baseline or a critictic function。

 So here's a paper that does something similar。 So this paper proposes a deep Rl method that foregoes the baseline function。

 and this is not the only paper that does this， but I'm just making the point that there are there were early attempts to do to remove the baseline function in these deep R methods。

 I'll also point out that it's not obvious that GRPO is the best or even a good enough algorithm to do reinforcement without a baseline or a critictic model。

 even when you restrict things to Lms。 So GRPO got really a lot of attention due to its use in training the deepse R1 model。

 which really did get a lot of attention for good reasons。

 But other approaches may replace GRPO in future work。

 So GRPO got a lot of attention not because GRPO is so good。

 GRPO got a lot of attention because it was used in deepse R1。

 And we should expect improvements upon GRPO or maybe even completely different algorithms to replace。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_70.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_71.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_72.png)

GRPO in the future， GRPO is not really has not yet stood the test of time。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_74.png)

And in fact， improving upon Geia will likely be a very active and fruitful area of research。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_76.png)

Okay， so then let's conclude this coverage of PPO and GRPO algorithms with a discussion of why it is that reinforcement learning with large language models don't really use other types of deep RL algorithms because there are those different types of deep RL algorithms do exist。

Well， here are some key properties of the reinforcement learning with large language model setup。

 So large language models have a finite action space。 So at each time step。

 a large language model needs to generate a token and a number of possible tokens。

 That's the action space。 The action space is not continuous。

 So that's one crucial part property of the RL LM setup。

Another crucial property is that we actually have a pretty good。

 a very powerful pretrained large language model of pi Theta。

 which serves as a suboptimal but reasonably good initial policy for the reinforcement learning that we are about to do。

 and that is an absolutely crucial component of RL LLM。In fact， if you just try Tular Raa RL methods。

 so this means you just randomly initialize a policy or language model and just try to do pure RL。

 that's just not going to work。 there's no chance that it works。

 So if you collect a bunch of math solve math problems。

 you just randomly initialize a transformer and have the transformer solve these math problems without in doing any language model pretraining。

 this will never， ever， ever work。So we expect a reinforcement learning method for RLLLM to work only if it can effectively utilize the pre trained large language model。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_78.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_79.png)

So in comparison， a DqN or a rainbow DQN， these are deep RL methods。

 these are very popular deep Rl methods， but these work by parameterizing the Q function as a neural network and learning the Q function by trying to solve fit thebdoin optimality equation once the Q function is learned。

 the policy which we did on as pi phi， this is implicitly derived through the greedy rule。

 So given the Q function we find the action that maximizes the Q function and we have the policy choose at action。

There is no explicitly parameterized policy in DQN。

 so the strength of the policy hinges on the accuracy of the Q function， the Q network。

 if the Q network approximates the true optimal Q function well。

 then the gradient policy will be good if this approximation is not good。

 then well the policy will not be good。If you think about how DQN works。

 there does not really seem to be a good way for DQN to utilize a pretrained policy。

 and if the RL method is not able to utilize the pre-trained large language model effectively。

 it's probably not going to be effective at performing reinforcement learning with these large language models。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_81.png)

DDPG， TD3 and SAC these are a different family of methods。

 these are methods that have dual interpretations as a deterministic policy gradientd method and these deterministic policy gradient methods I'll just say that these are qualitatively quite different from these stochastic policy graded methods。

 which is the policy graded methods that we've seen so far。😊。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_83.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_84.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_85.png)

And also these methods， DDPG T23 and ZAC， they have the dual interpretation as also as a Q learning type method。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_87.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_88.png)

These methods are designed for continuous action spaces。

 although there is a variant called Sac discrete， which applies to a discrete action spaces。

 So one could imagine applying Sac discrete for the reinforcement learning of large language models。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_90.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_91.png)

Now these methods， they train both a policy， pi theta and a Q function， Q the Q network Q P。

 but different from PPO， the pi theta is not trained directly to maximize reward。

 rather pi theta is trained to satisfy the relation。

 the greedy relation where pi theta is trained to approximate the arggonm of the Q network。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_93.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_94.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_95.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_96.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_97.png)

So in PPO， the rewards directly influence the updates of the policy pi theta， whereas in DDPG。

 TD3 and SAC， the rewards influence the Q function， which in turn influences pi the policy pi theta。

 so the updates on pi theta depend on the rewards only through the Q function。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_99.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_100.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_101.png)

But in the setting of reinforcement learning on large language models， we have a good initialization。

 We have a good pretrained model for the policy pi。

 but we don't have a good initialization for the Q function。

 So with when we only have a good initialization for pi。

 that alone seems difficult to utilize effectively。

 So because we only have a good initialization for pi theta and not for Q。😊。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_103.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_104.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_105.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_106.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_107.png)

And because different from PPO， the accuracy of Q is much more important in these sactype methods。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_109.png)

![](img/294d57c980c5d60a2c8cbbc42365d5aa_110.png)

It's probably difficult to effectively utilize these methods for reinforcement learning on large language models。



![](img/294d57c980c5d60a2c8cbbc42365d5aa_112.png)